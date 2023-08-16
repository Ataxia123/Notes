---
id: "multisig-dev"
aliases:
  - "Multisig dev Notes "
  - "Multisig dev Notes"
tags: []
---
[[At0x-Scratchpad|Based and very redpilled notes ]]
# Multisig dev Notes


## DELEGATE CONTRACT
// TODO: 
- Test Multisig contract normal implementation
- Run standalone chainlink test
- Test Multisig contract with chainlink function
- Inherits Multisig method && chainlink Method
### Contract Lifecycle
1) Deployed with constructor arguments:
   - DELEGATE
   - Governor contract
   - Params:
     -Quorum
     Proposal length
2) Delegate creates proposal:
  - calldata
3) Vote happens in snapshot
4) Delegate executes proposal check
   - returns requestID
5) Check requestID and execute proposal
 - Check return of chainlink function
    - YAY = prop execute
    - NAY = prop marked as failed
    - ELSE = prop in progress or quorum not met.
- 
### EXECUTE FUNCTION
	
// TODO: refactor this function to use Chainlink to verify offchain vote
		// 1) bring the chf into hardhat run it standalone w the script
    // 2) import functionConsumer.sol infto multisig
    // 3) define _useChainlink() in multisig
    // 4) write test script.
⚠️//NOTE: Request triggers an event on chain
Vote verification process will happen in two steps:
-> chainlink Function request ID for the proposal
-> On chain execution of function reading the result on chain.

//NOTE: if the fx fails, whats the return??? 
   "0x1231 = yay | 01211313 = nay | 0x123123 = abstain| not finished"
tx start---> chainlink query ---> chainlink result ---> tx continue 
-------------------------------------------------------> if query = not 

### CHAINLINK FUNCTIONS TEMPLATE JS CALL

```JavaScript

const { getDecodedResultLog, getRequestConfig } = require("../../FunctionsSandboxLibrary")
const { generateRequest } = require("./buildRequestJSON")
const { networks } = require("../../networks")
const utils = require("../utils")
const chalk = require("chalk")
const { deleteGist } = require("../utils/github")
const { RequestStore } = require("../utils/artifact")
const path = require("path")
const process = require("process")

task("functions-request", "Initiates a request from a Functions client contract")
  .addParam("contract", "Address of the client contract to call")
  .addParam("subid", "Billing subscription ID used to pay for the request")
  .addOptionalParam(
    "simulate",
    "Flag indicating if simulation should be run before making an on-chain request",
    true,
    types.boolean
  )
  .addOptionalParam(
    "gaslimit",
    "Maximum amount of gas that can be used to call fulfillRequest in the client contract",
    100000,
    types.int
  )
  .addOptionalParam("requestgas", "Gas limit for calling the executeRequest function", 1_500_000, types.int)
  .addOptionalParam(
    "configpath",
    "Path to Functions request config file",
    `${__dirname}/../../Functions-request-config.js`,
    types.string
  )
  .setAction(async (taskArgs, hre) => {
    // A manual gas limit is required as the gas limit estimated by Ethers is not always accurate
    const overrides = {
      gasLimit: taskArgs.requestgas,
      gasPrice: networks[network.name].gasPrice,
    }

    if (network.name === "hardhat") {
      throw Error(
        'This command cannot be used on a local development chain.  Specify a valid network or simulate an Functions request locally with "npx hardhat functions-simulate".'
      )
    }

    // Get the required parameters
    const contractAddr = taskArgs.contract
    const subscriptionId = taskArgs.subid
    const gasLimit = taskArgs.gaslimit
    if (gasLimit > 300000) {
      throw Error("Gas limit must be less than or equal to 300,000")
    }

    // Attach to the required contracts
    const clientContractFactory = await ethers.getContractFactory("FunctionsConsumer")
    const clientContract = clientContractFactory.attach(contractAddr)
    const OracleFactory = await ethers.getContractFactory("contracts/dev/functions/FunctionsOracle.sol:FunctionsOracle")
    const oracle = await OracleFactory.attach(networks[network.name]["functionsOracleProxy"])
    const registryAddress = await oracle.getRegistry()
    const RegistryFactory = await ethers.getContractFactory(
      "contracts/dev/functions/FunctionsBillingRegistry.sol:FunctionsBillingRegistry"
    )
    const registry = await RegistryFactory.attach(registryAddress)

    // Check that the subscription is valid
    let subInfo
    try {
      subInfo = await registry.getSubscription(subscriptionId)
    } catch (error) {
      if (error.errorName === "InvalidSubscription") {
        throw Error(`Subscription ID "${subscriptionId}" is invalid or does not exist`)
      }
      throw error
    }
    // Validate the client contract has been authorized to use the subscription
    const existingConsumers = subInfo[2].map((addr) => addr.toLowerCase())
    if (!existingConsumers.includes(contractAddr.toLowerCase())) {
      throw Error(`Consumer contract ${contractAddr} is not registered to use subscription ${subscriptionId}`)
    }

    const unvalidatedRequestConfig = require(path.isAbsolute(taskArgs.configpath)
      ? taskArgs.configpath
      : path.join(process.cwd(), taskArgs.configpath))
    const requestConfig = getRequestConfig(unvalidatedRequestConfig)

    const simulatedSecretsURLBytes = `0x${Buffer.from(
      "https://exampleSecretsURL.com/f09fa0db8d1c8fab8861ec97b1d7fdf1/raw/d49bbd20dc562f035bdf8832399886baefa970c9/encrypted-functions-request-data-1679941580875.json"
    ).toString("hex")}`

    // Estimate the cost of the request
    const { lastBaseFeePerGas, maxPriorityFeePerGas } = await hre.ethers.provider.getFeeData()
    const estimatedCostJuels = await clientContract.estimateCost(
      [
        requestConfig.codeLocation,
        1, // SecretsLocation: Remote
        requestConfig.codeLanguage,
        requestConfig.source,
        requestConfig.secrets && Object.keys(requestConfig.secrets).length > 0 ? simulatedSecretsURLBytes : [],
        requestConfig.args ?? [],
      ],
      subscriptionId,
      gasLimit,
      maxPriorityFeePerGas.add(lastBaseFeePerGas)
    )
    const estimatedCostLink = hre.ethers.utils.formatUnits(estimatedCostJuels, 18)

    // Ensure that the subscription has a sufficient balance
    const subBalanceInJules = subInfo[0]
    const linkBalance = hre.ethers.utils.formatUnits(subBalanceInJules, 18)

    if (subBalanceInJules.lt(estimatedCostJuels)) {
      throw Error(
        `Subscription ${subscriptionId} does not have sufficient funds. The estimated cost is ${estimatedCostLink} LINK, but the subscription only has a balance of ${linkBalance} LINK`
      )
    }

    const transactionEstimateGas = await clientContract.estimateGas.executeRequest(
      requestConfig.source,
      requestConfig.secrets && Object.keys(requestConfig.secrets).length > 0 ? simulatedSecretsURLBytes : [],
      requestConfig.args ?? [],
      subscriptionId,
      gasLimit,
      overrides
    )

    await utils.promptTxCost(transactionEstimateGas, hre, true)

    // Print the estimated cost of the request
    // Ask for confirmation before initiating the request on-chain
    await utils.prompt(
      `If the request's callback uses all ${utils.numberWithCommas(
        gasLimit
      )} gas, this request will charge the subscription:\n${chalk.blue(estimatedCostLink + " LINK")}`
    )
    //  TODO: add cost of this LINK in USD

    // doGistCleanup indicates if an encrypted secrets Gist was created automatically and should be cleaned up once the request is complete
    let doGistCleanup = !(requestConfig.secretsURLs && requestConfig.secretsURLs.length > 0)
    const request = await generateRequest(requestConfig, taskArgs)
    doGistCleanup = doGistCleanup && request.secrets

    const store = new RequestStore(hre.network.config.chainId, network.name, "consumer")

    const spinner = utils.spin({
      text: `Submitting transaction for FunctionsConsumer contract ${contractAddr} on network ${network.name}`,
    })

    // Use a promise to wait & listen for the fulfillment event before returning
    await new Promise(async (resolve, reject) => {
      let requestId

      let cleanupInProgress = false
      const cleanup = async () => {
        spinner.stop()
        if (doGistCleanup) {
          if (!cleanupInProgress) {
            cleanupInProgress = true
            const success = await deleteGist(process.env["GITHUB_API_TOKEN"], request.secretsURLs[0].slice(0, -4))
            if (success) {
              await store.update(requestId, { activeManagedSecretsURLs: false })
            }
            return resolve()
          }
          return
        }
        return resolve()
      }

      // Initiate the listeners before making the request
      // Listen for fulfillment errors
      oracle.on("UserCallbackError", async (eventRequestId, msg) => {
        if (requestId == eventRequestId) {
          spinner.fail(
            "Error encountered when calling fulfillRequest in client contract.\n" +
              "Ensure the fulfillRequest function in the client contract is correct and the --gaslimit is sufficient."
          )
          console.log(`${msg}\n`)
          await store.update(requestId, { status: "failed", error: msg })
          await cleanup()
        }
      })
      oracle.on("UserCallbackRawError", async (eventRequestId, msg) => {
        if (requestId == eventRequestId) {
          spinner.fail("Raw error in contract request fulfillment. Please contact Chainlink support.")
          console.log(Buffer.from(msg, "hex").toString())
          await store.update(requestId, { status: "failed", error: msg })
          await cleanup()
        }
      })
      // Listen for successful fulfillment, both must be true to be finished
      let billingEndEventReceived = false
      let ocrResponseEventReceived = false
      clientContract.on("OCRResponse", async (eventRequestId, result, err) => {
        // Ensure the fulfilled requestId matches the initiated requestId to prevent logging a response for an unrelated requestId
        if (eventRequestId !== requestId) {
          return
        }

        spinner.succeed(`Request ${requestId} fulfilled! Data has been written on-chain.\n`)
        if (result !== "0x") {
          console.log(
            `Response returned to client contract represented as a hex string: ${result}\n${getDecodedResultLog(
              requestConfig,
              result
            )}`
          )
        }
        if (err !== "0x") {
          console.log(`Error message returned to client contract: "${Buffer.from(err.slice(2), "hex")}"\n`)
        }
        ocrResponseEventReceived = true
        await store.update(requestId, { status: "complete", result })

        if (billingEndEventReceived) {
          await cleanup()
        }
      })
      // Listen for the BillingEnd event, log cost breakdown & resolve
      registry.on(
        "BillingEnd",
        async (
          eventRequestId,
          eventSubscriptionId,
          eventSignerPayment,
          eventTransmitterPayment,
          eventTotalCost,
          eventSuccess
        ) => {
          if (requestId == eventRequestId) {
            const baseFee = eventTotalCost.sub(eventTransmitterPayment)
            spinner.stop()
            console.log(`Actual amount billed to subscription #${subscriptionId}:`)
            const costBreakdownData = [
              {
                Type: "Transmission cost:",
                Amount: `${hre.ethers.utils.formatUnits(eventTransmitterPayment, 18)} LINK`,
              },
              { Type: "Base fee:", Amount: `${hre.ethers.utils.formatUnits(baseFee, 18)} LINK` },
              { Type: "", Amount: "" },
              { Type: "Total cost:", Amount: `${hre.ethers.utils.formatUnits(eventTotalCost, 18)} LINK` },
            ]
            utils.logger.table(costBreakdownData)

            // Check for a successful request
            billingEndEventReceived = true
            if (ocrResponseEventReceived) {
              await cleanup()
            }
          }
        }
      )

      let requestTx
      try {
        // Initiate the on-chain request after all listeners are initialized
        requestTx = await clientContract.executeRequest(
          request.source,
          request.secrets ?? [],
          request.args ?? [],
          subscriptionId,
          gasLimit,
          overrides
        )
      } catch (error) {
        // If the request fails, ensure the encrypted secrets Gist is deleted
        if (doGistCleanup) {
          await deleteGist(process.env["GITHUB_API_TOKEN"], request.secretsURLs[0].slice(0, -4))
        }
        throw error
      }
      spinner.start("Waiting 2 blocks for transaction to be confirmed...")
      const requestTxReceipt = await requestTx.wait(2)
      spinner.info(
        `Transaction confirmed, see ${
          utils.getEtherscanURL(network.config.chainId) + "tx/" + requestTx.hash
        } for more details.`
      )
      spinner.stop()
      requestId = requestTxReceipt.events[2].args.id
      spinner.start(
        `Request ${requestId} has been initiated. Waiting for fulfillment from the Decentralized Oracle Network...\n`
      )
      await store.create({
        type: "consumer",
        requestId,
        transactionReceipt: requestTxReceipt,
        taskArgs,
        codeLocation: requestConfig.codeLocation,
        codeLanguage: requestConfig.codeLanguage,
        source: requestConfig.source,
        secrets: requestConfig.secrets,
        perNodeSecrets: requestConfig.perNodeSecrets,
        secretsURLs: request.secretsURLs,
        activeManagedSecretsURLs: doGistCleanup,
        args: requestConfig.args,
        expectedReturnType: requestConfig.expectedReturnType,
        DONPublicKey: requestConfig.DONPublicKey,
      })
      // If a response is not received in time, the request has exceeded the Service Level Agreement
      setTimeout(async () => {
        spinner.fail(
          "A response has not been received within 5 minutes of the request being initiated and has been canceled. Your subscription was not charged. Please make a new request."
        )
        await store.update(requestId, { status: "pending_timed_out" })
        reject()
      }, 300_000) // TODO: use registry timeout seconds
    })
  })

```

### Chainlink functions LIBRARY

#### 1) Average price API call Sample function call:

```JavaScript

// This example shows how to make a decentralized price feed using multiple APIs

// Arguments can be provided when a request is initated on-chain and used in the request source code as shown below
const coinMarketCapCoinId = args[0]
const coinGeckoCoinId = args[1]
const coinPaprikaCoinId = args[2]
const badApiCoinId = args[3]

if (
  secrets.apiKey == "" ||
  secrets.apiKey === "Your coinmarketcap API key (get a free one: https://coinmarketcap.com/api/)"
) {
  throw Error(
    "COINMARKETCAP_API_KEY environment variable not set for CoinMarketCap API.  Get a free key from https://coinmarketcap.com/api/"
  )
}

// To make an HTTP request, use the Functions.makeHttpRequest function
// Functions.makeHttpRequest function parameters:
// - url
// - method (optional, defaults to 'GET')
// - headers: headers supplied as an object (optional)
// - params: URL query parameters supplied as an object (optional)
// - data: request body supplied as an object (optional)
// - timeout: maximum request duration in ms (optional, defaults to 10000ms)
// - responseType: expected response type (optional, defaults to 'json')

// Use multiple APIs & aggregate the results to enhance decentralization
const coinMarketCapRequest = Functions.makeHttpRequest({
  url: `https://pro-api.coinmarketcap.com/v1/cryptocurrency/quotes/latest?convert=USD&id=${coinMarketCapCoinId}`,
  // Get a free API key from https://coinmarketcap.com/api/
  headers: { "X-CMC_PRO_API_KEY": secrets.apiKey },
})
const coinGeckoRequest = Functions.makeHttpRequest({
  url: `https://api.coingecko.com/api/v3/simple/price?ids=${coinGeckoCoinId}&vs_currencies=usd`,
})
const coinPaprikaRequest = Functions.makeHttpRequest({
  url: `https://api.coinpaprika.com/v1/tickers/${coinPaprikaCoinId}`,
})
// This dummy request simulates a failed API request
const badApiRequest = Functions.makeHttpRequest({
  url: `https://badapi.com/price/symbol/${badApiCoinId}`,
})

// First, execute all the API requests are executed concurrently, then wait for the responses
const [coinMarketCapResponse, coinGeckoResponse, coinPaprikaResponse, badApiResponse] = await Promise.all([
  coinMarketCapRequest,
  coinGeckoRequest,
  coinPaprikaRequest,
  badApiRequest,
])

const prices = []

if (!coinMarketCapResponse.error) {
  prices.push(coinMarketCapResponse.data.data[coinMarketCapCoinId].quote.USD.price)
} else {
  console.log("CoinMarketCap Error")
}
if (!coinGeckoResponse.error) {
  prices.push(coinGeckoResponse.data[coinGeckoCoinId].usd)
} else {
  console.log("CoinGecko Error")
}
if (!coinPaprikaResponse.error) {
  prices.push(coinPaprikaResponse.data.quotes.USD.price)
} else {
  console.log("CoinPaprika Error")
}
// A single failed API request does not cause the whole request to fail
if (!badApiResponse.error) {
  prices.push(httpResponses[3].data.price.usd)
} else {
  console.log(
    "Bad API request failed. (This message is expected to demonstrate using console.log for debugging locally with the simulator)"
  )
}

// At least 3 out of 4 prices are needed to aggregate the median price
if (prices.length < 3) {
  // If an error is thrown, it will be returned back to the smart contract
  throw Error("More than 1 API failed")
}

const medianPrice = prices.sort((a, b) => a - b)[Math.round(prices.length / 2)]
console.log(`Median Bitcoin price: $${medianPrice.toFixed(2)}`)

// The source code MUST return a Buffer or the request will return an error message
// Use one of the following functions to convert to a Buffer representing the response bytes that are returned to the client smart contract:
// - Functions.encodeUint256
// - Functions.encodeInt256
// - Functions.encodeString
// Or return a custom Buffer for a custom byte encoding
return Functions.encodeUint256(Math.round(medianPrice * 100))

```
## FUNCTION CONSUMER CONTRACT

```solidity
  function execute(
		address[] memory targets,
		uint256[] memory values,
		bytes[] memory calldatas,
		bytes32 descriptionHash
	) external onlyExecutors {
		uint256 id = _hashProposal(targets, values, calldatas, descriptionHash);
		Proposal storage proposal = proposals[id];
    uint256 result = _chainlinkQuery(proposal.id); //<- Uint256
finished, revert
	
if (result == "not finished") revert ("Chainlink query not finished") else if {
  ( result == "Quorum Not met") revert ("Quorum not met") 
```

## CHAINLINK FUNCTIONS SAMPLE CONTRACT

```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.7;

import {Functions, FunctionsClient} from "./dev/functions/FunctionsClient.sol";
// import "@chainlink/contracts/src/v0.8/dev/functions/FunctionsClient.sol"; // Once published
import {ConfirmedOwner} from "@chainlink/contracts/src/v0.8/ConfirmedOwner.sol";

/**
 * @title Functions Consumer contract
 * @notice This contract is a demonstration of using Functions.
 * @notice NOT FOR PRODUCTION USE
 */
contract FunctionsConsumer is FunctionsClient, ConfirmedOwner {
  using Functions for Functions.Request;

  bytes32 public latestRequestId;
  bytes public latestResponse;
  bytes public latestError;

  event OCRResponse(bytes32 indexed requestId, bytes result, bytes err);

  /**
   * @notice Executes once when a contract is created to initialize state variables
   *
   * @param oracle - The FunctionsOracle contract
   */
  // https://github.com/protofire/solhint/issues/242
  // solhint-disable-next-line no-empty-blocks
  constructor(address oracle) FunctionsClient(oracle) ConfirmedOwner(msg.sender) {}

  /**
   * @notice Send a simple request
   *
   * @param source JavaScript source code
   * @param secrets Encrypted secrets payload
   * @param args List of arguments accessible from within the source code
   * @param subscriptionId Funtions billing subscription ID
   * @param gasLimit Maximum amount of gas used to call the client contract's `handleOracleFulfillment` function
   * @return Functions request ID
   */
  function executeRequest(
    string calldata source,
    bytes calldata secrets,
    string[] calldata args,
    uint64 subscriptionId,
    uint32 gasLimit
  ) public onlyOwner returns (bytes32) {
    Functions.Request memory req;
    req.initializeRequest(Functions.Location.Inline, Functions.CodeLanguage.JavaScript, source);
    if (secrets.length > 0) {
      req.addRemoteSecrets(secrets);
    }
    if (args.length > 0) req.addArgs(args);

    bytes32 assignedReqID = sendRequest(req, subscriptionId, gasLimit);
    latestRequestId = assignedReqID;
    return assignedReqID;
  }

  /**
   * @notice Callback that is invoked once the DON has resolved the request or hit an error
   *
   * @param requestId The request ID, returned by sendRequest()
   * @param response Aggregated response from the user code
   * @param err Aggregated error from the user code or from the execution pipeline
   * Either response or error parameter will be set, but never both
   */
  function fulfillRequest(bytes32 requestId, bytes memory response, bytes memory err) internal override {
    latestResponse = response;
    latestError = err;
    emit OCRResponse(requestId, response, err);
  }

  /**
   * @notice Allows the Functions oracle address to be updated
   *
   * @param oracle New oracle address
   */
  function updateOracleAddress(address oracle) public onlyOwner {
    setOracle(oracle);
  }

  function addSimulatedRequestId(address oracleAddress, bytes32 requestId) public onlyOwner {
    addExternalRequest(oracleAddress, requestId);
  }
}
```
