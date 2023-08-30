
 

[.github](/hydra-net/vanilla-lnd/tree/master/.github ".github")

[build: bump min Go version to 1.19](/hydra-net/vanilla-lnd/commit/0bbbd9b911e4fd501a18b7f699f53e104e63f3d1 "build: bump min Go version to 1.19
Fixes https://github.com/lightningnetwork/lnd/issues/7495")

March 8, 2023 18:02

[.vscode](/hydra-net/vanilla-lnd/tree/master/.vscode ".vscode")

[.vscode: add editor settings for VS Code](/hydra-net/vanilla-lnd/commit/d20140e39337753dc82e1f14155c203f8bc61463 ".vscode: add editor settings for VS Code")

July 6, 2022 10:25

[aezeed](/hydra-net/vanilla-lnd/tree/master/aezeed "aezeed")

[multi: add new build tag `integration`](/hydra-net/vanilla-lnd/commit/edba93899647afde968e09690bd557d19722e5d0 "multi: add new build tag `integration`
This commit adds a new build tag `integration` and removes the old tag
`rpctest` for clarity. Multiple unnecessary usages of `build !rpctest`
is also removed.")

February 23, 2023 21:56

[aliasmgr](/hydra-net/vanilla-lnd/tree/master/aliasmgr "aliasmgr")

[aliasmgr: export StartingAlias so other packages can use it](/hydra-net/vanilla-lnd/commit/feb8e7e64e276dc3ea24b0c30a32fcfbd7caa628 "aliasmgr: export StartingAlias so other packages can use it")

January 25, 2023 12:03

[amp](/hydra-net/vanilla-lnd/tree/master/amp "amp")

[multi: fix `make fmt`](/hydra-net/vanilla-lnd/commit/0735522194a820b76d7d2d358ee8b792daf1e356 "multi: fix `make fmt`")

August 23, 2022 22:10

[autopilot](/hydra-net/vanilla-lnd/tree/master/autopilot "autopilot")

[autopilot: fix loop variables, use require](/hydra-net/vanilla-lnd/commit/8d6befd7979bfa4cd48ad2aa082d586b426e478b "autopilot: fix loop variables, use require
With this commit we fix a few occurrences of loop variables being
accessed in closures.
While we touch the code, we also migrate it to using the require
library.")

October 13, 2022 14:40

[batch](/hydra-net/vanilla-lnd/tree/master/batch "batch")

[kvdb: move channeldb/kvdb to top level](/hydra-net/vanilla-lnd/commit/14c851c8fc5f0e8419eb264df05575b1cf5f053e "kvdb: move channeldb/kvdb to top level")

May 7, 2021 14:18

[blockcache](/hydra-net/vanilla-lnd/tree/master/blockcache "blockcache")

[multi: bump neutrino+btcwallet versions, use new generic lru cache](/hydra-net/vanilla-lnd/commit/a15c45231e73da73cb6b89a18f7f2eb775fea2bc "multi: bump neutrino+btcwallet versions, use new generic lru cache")

February 21, 2023 17:28

[brontide](/hydra-net/vanilla-lnd/tree/master/brontide "brontide")

[brontide,lnwire,wtwire,zpay32: appease linter](/hydra-net/vanilla-lnd/commit/e15d3e898ed5f4226ff46a41ef839a5f08cc70ad "brontide,lnwire,wtwire,zpay32: appease linter
Address all linter complaints for the newly migrated fuzz tests.")

November 11, 2022 08:44

[buffer](/hydra-net/vanilla-lnd/tree/master/buffer "buffer")

[lnwire: remove unused MaxMessagePayload const](/hydra-net/vanilla-lnd/commit/4b12f40a48e580f3b34b7f43eb600b3aaed787b2 "lnwire: remove unused MaxMessagePayload const
MaxMessagePayload and MaxSliceLength are duplicate variables. This
commit deletes MaxMessagePayload and keeps MaxSliceLength.")

August 10, 2021 05:36

[build](/hydra-net/vanilla-lnd/tree/master/build "build")

[build: bump version to v0.16.0-rc3](/hydra-net/vanilla-lnd/commit/840c939464fd75d7de814579d72290d251ae82f8 "build: bump version to v0.16.0-rc3")

March 10, 2023 19:09

[cert](/hydra-net/vanilla-lnd/tree/master/cert "cert")

[cert: removed unused args from cert.GenCertPair](/hydra-net/vanilla-lnd/commit/c3445e79d99da5d69e56cc1a0411feb72c7466f4 "cert: removed unused args from cert.GenCertPair
Since the cert pair is written with a subsequent call to
cert.WriteCertPair we can safely remove the two file paths from the
argument list of cert.GenCertPair.")

February 6, 2023 17:11

[chainntnfs](/hydra-net/vanilla-lnd/tree/master/chainntnfs "chainntnfs")

[chainntnfs: fix temp dir creation and rpcpolling switch](/hydra-net/vanilla-lnd/commit/7bf4eee68537efc3d52b4499020e5ff9604f5812 "chainntnfs: fix temp dir creation and rpcpolling switch
In the NewBitcoindBackend test util function, ensure that the
`rpcpolling` param is switched on in the correct order. Also switch back
to using `ioutil.TempDir` as it seems that the zmq conn strings created
from `t.TempDir()` result in an invalid conn string.")

March 7, 2023 08:45

[chainreg](/hydra-net/vanilla-lnd/tree/master/chainreg "chainreg")

[chainntnfs: move cache implementation to channeldb](/hydra-net/vanilla-lnd/commit/c602ac07e7834dacba8571e0c7bbf54bc5f441c5 "chainntnfs: move cache implementation to channeldb
This commit moves the `HeightHintCache` implementation to the
`channeldb` package and inverts the dependency relation between
`chainntnfs` and `channeldb`.
Many packages depend on channeldb for type definitions,
interfaces, etc. `chainntnfs` is an example of that. `chainntnfs`
defines the  `SpendHintCache` and `ConfirmHintCache` interfaces but
it also implments them (`HeightHintCache` struct). The implementation
uses logic that should not leak from channeldb (ex: bucket paths).
This makes our code highly coupled + it would not allow us to use any
of these interfaces in a package that is imported by `channeldb`
(circular dependency).")

January 16, 2023 03:13

[chanacceptor](/hydra-net/vanilla-lnd/tree/master/chanacceptor "chanacceptor")

[rpc: validate closing channel address in open channel requests](/hydra-net/vanilla-lnd/commit/2204cbfd30736aec11bad485b97fdf379c3ec318 "rpc: validate closing channel address in open channel requests
Our OpenChannelRPC was accepting invalid values for the closing address
field. If we were able to decode the address we would use it in the
script even if the address is for another bitcoin net.")

January 4, 2023 04:42

[chanbackup](/hydra-net/vanilla-lnd/tree/master/chanbackup "chanbackup")

[chanbackup: replace defer cleanup with `t.Cleanup`](/hydra-net/vanilla-lnd/commit/5c5997935deea575e5ef68a15bf58d887591cc90 "chanbackup: replace defer cleanup with `t.Cleanup`
Signed-off-by: Eng Zer Jun <engzerjun@gmail.com>")

October 13, 2022 17:01

[chanfitness](/hydra-net/vanilla-lnd/tree/master/chanfitness "chanfitness")

[fix typos [skip ci]](/hydra-net/vanilla-lnd/commit/3dc5ddc16891bd718ea977dadd6f30fa59e21726 "fix typos [skip ci]")

April 11, 2022 18:26

[channeldb](/hydra-net/vanilla-lnd/tree/master/channeldb "channeldb")

[Merge pull request](/hydra-net/vanilla-lnd/commit/b3e27f9ba7585de24bf0c5c2a9a52571093ce4dd "Merge pull request #7415 from bitromortac/2302-max-htlc
routing+discovery: fail non-maxHTLC channel updates in validation") [lightningnetwork#7415](https://github.com/lightningnetwork/lnd/pull/7415) [from bitromortac/2302-max-htlc](/hydra-net/vanilla-lnd/commit/b3e27f9ba7585de24bf0c5c2a9a52571093ce4dd "Merge pull request #7415 from bitromortac/2302-max-htlc
routing+discovery: fail non-maxHTLC channel updates in validation")

February 22, 2023 08:45

[channelnotifier](/hydra-net/vanilla-lnd/tree/master/channelnotifier "channelnotifier")

[channelnotifier: add `InactiveLinkEvent`](/hydra-net/vanilla-lnd/commit/ced883389508b7601c37e5957f546dfb59e8bfbf "channelnotifier: add `InactiveLinkEvent`
This commit adds a new event `InactiveLinkEvent` to be used when a link
becomes inactive.")

January 18, 2023 03:46

[clock](/hydra-net/vanilla-lnd/tree/master/clock "clock")

[clock: add missing package `require` and replace `assert` [skip ci]](/hydra-net/vanilla-lnd/commit/077ebe386810abb8d2d079dbc62c895e78e664c2 "clock: add missing package `require` and replace `assert` [skip ci]")

August 23, 2022 03:27

[cluster](/hydra-net/vanilla-lnd/tree/master/cluster "cluster")

[cluster: replace defer cleanup with `t.Cleanup`](/hydra-net/vanilla-lnd/commit/100839fcead6d6886312b6b85dcb3a227b36dd78 "cluster: replace defer cleanup with `t.Cleanup`
Signed-off-by: Eng Zer Jun <engzerjun@gmail.com>")

October 13, 2022 17:47

[cmd](/hydra-net/vanilla-lnd/tree/master/cmd "cmd")

[Merge pull request](/hydra-net/vanilla-lnd/commit/251802d7961d7158f374b19f34131749a4ab59eb "Merge pull request #7444 from bitromortac/2302-capacity-config
routing: configurable capacity fraction for apriori probability") [lightningnetwork#7444](https://github.com/lightningnetwork/lnd/pull/7444) [from bitromortac/2302-capaci…](/hydra-net/vanilla-lnd/commit/251802d7961d7158f374b19f34131749a4ab59eb "Merge pull request #7444 from bitromortac/2302-capacity-config
routing: configurable capacity fraction for apriori probability")

March 2, 2023 18:39

[contractcourt](/hydra-net/vanilla-lnd/tree/master/contractcourt "contractcourt")

[multi: add new build tag `integration`](/hydra-net/vanilla-lnd/commit/edba93899647afde968e09690bd557d19722e5d0 "multi: add new build tag `integration`
This commit adds a new build tag `integration` and removes the old tag
`rpctest` for clarity. Multiple unnecessary usages of `build !rpctest`
is also removed.")

February 23, 2023 21:56

[contrib](/hydra-net/vanilla-lnd/tree/master/contrib "contrib")

[docs: remove PIDFile from example systemd service](/hydra-net/vanilla-lnd/commit/9ba341bd95c5eee52d2d719cd7531b4ed70201c7 "docs: remove PIDFile from example systemd service")

January 11, 2022 14:08

[discovery](/hydra-net/vanilla-lnd/tree/master/discovery "discovery")

[discovery+server: add more trace log](/hydra-net/vanilla-lnd/commit/f22b25a1bf0382e18003db1eef8b5b803b578562 "discovery+server: add more trace log")

March 8, 2023 21:02

[docker](/hydra-net/vanilla-lnd/tree/master/docker "docker")

[scripted-diff: replace ⛰ emoji with $ [skip ci]](/hydra-net/vanilla-lnd/commit/0b1e881d18aa186c99f5c8f06963d39320c1629d "scripted-diff: replace ⛰  emoji with $ [skip ci]
-BEGIN VERIFY SCRIPT-
sed -i 's/⛰/$/g' $(git grep -l '⛰')
-END VERIFY SCRIPT-")

October 28, 2022 12:06

[docs](/hydra-net/vanilla-lnd/tree/master/docs "docs")

[docs/release-notes: add note for new tx rebroadcast](/hydra-net/vanilla-lnd/commit/6b8a1f1d67645c71280f3f2f59e8e4f31fb1c542 "docs/release-notes: add note for new tx rebroadcast")

March 10, 2023 19:07

[feature](/hydra-net/vanilla-lnd/tree/master/feature "feature")

[feature+lncfg: add config option to turn of anysegwit](/hydra-net/vanilla-lnd/commit/89529fbb4feedecaf0af301386de549cf649d5d8 "feature+lncfg: add config option to turn of anysegwit")

August 10, 2022 18:44

[funding](/hydra-net/vanilla-lnd/tree/master/funding "funding")

[funding: fix itest flake with pending channels](/hydra-net/vanilla-lnd/commit/3f6315242a7ceb160c12f6997f5c020362424877 "funding: fix itest flake with pending channels")

February 24, 2023 01:35

[healthcheck](/hydra-net/vanilla-lnd/tree/master/healthcheck "healthcheck")

[build(deps): bump golang.org/x/sys in /healthcheck](/hydra-net/vanilla-lnd/commit/fccfefdb5820730c83485c706a314c03fdf59f8c "build(deps): bump golang.org/x/sys in /healthcheck
Bumps [golang.org/x/sys](https://github.com/golang/sys) from 0.0.0-20211216021012-1d35b9e2eb4e to 0.1.0.
- [Release notes](https://github.com/golang/sys/releases)
- [Commits](https://github.com/golang/sys/commits/v0.1.0)
---
updated-dependencies:
- dependency-name: golang.org/x/sys
dependency-type: direct:production
...
Signed-off-by: dependabot[bot] <support@github.com>")

February 25, 2023 08:08

[htlcswitch](/hydra-net/vanilla-lnd/tree/master/htlcswitch "htlcswitch")

[htlcswitch: fix HandleChannelUpdate by selecting on link's quit chan](/hydra-net/vanilla-lnd/commit/53fa13bc299adcd40903104c33cb77ca76dab17c "htlcswitch: fix HandleChannelUpdate by selecting on link's quit chan")

February 23, 2023 21:56

[input](/hydra-net/vanilla-lnd/tree/master/input "input")

[multi: add version to MuSig2 API, bump btcd/btcec to v2.3.2](/hydra-net/vanilla-lnd/commit/ce5fa2e04307b8b74570356d4a70d489fa33097a "multi: add version to MuSig2 API, bump btcd/btcec to v2.3.2
With this commit we bump the github.com/btcd/btcec/v2 library to v2.3.2
which implements the MuSig2 BIP version v1.0.0rc2. With this the
github.com/btcsuite/btcd/btcec/v2/schnorr/musig2 package becomes
v1.0.0rc2 and the github.com/lightningnetwork/lnd/internal/musig2v040
stays at the old v0.4.0 version.")

February 3, 2023 18:30

[internal/musig2v040](/hydra-net/vanilla-lnd/tree/master/internal/musig2v040 "This path skips through empty directories")

[internal/musig2: rename to musig2v040 to avoid confusion](/hydra-net/vanilla-lnd/commit/0154226233885885315aceab68341a99083c381f "internal/musig2: rename to musig2v040 to avoid confusion
Since we explicitly keep an old version of a library in lnd for backward
compatibility we want to make sure the purpose and version of it is
clear and not misleading.")

February 3, 2023 18:30

[invoices](/hydra-net/vanilla-lnd/tree/master/invoices "invoices")

[invoices: fix flake in `TestInvoiceExpiryWithRegistry`](/hydra-net/vanilla-lnd/commit/4a7d3bc9c20f4683997856df96040d2ea62ccc2d "invoices: fix flake in `TestInvoiceExpiryWithRegistry`")

February 10, 2023 20:52

[itest](/hydra-net/vanilla-lnd/tree/master/itest "itest")

[Merge pull request](/hydra-net/vanilla-lnd/commit/251802d7961d7158f374b19f34131749a4ab59eb "Merge pull request #7444 from bitromortac/2302-capacity-config
routing: configurable capacity fraction for apriori probability") [lightningnetwork#7444](https://github.com/lightningnetwork/lnd/pull/7444) [from bitromortac/2302-capaci…](/hydra-net/vanilla-lnd/commit/251802d7961d7158f374b19f34131749a4ab59eb "Merge pull request #7444 from bitromortac/2302-capacity-config
routing: configurable capacity fraction for apriori probability")

March 2, 2023 18:39

[keychain](/hydra-net/vanilla-lnd/tree/master/keychain "keychain")

[mod+keychain+lntest: bump btcd to version with tweak fix](/hydra-net/vanilla-lnd/commit/e3536dd770a11b6be6e9c060ae752f4fbc0736f2 "mod+keychain+lntest: bump btcd to version with tweak fix
This commit bumps to the latest version of btcd that fixes a key
mutation issue when signing for Taproot outputs.")

November 11, 2022 10:20

[kvdb](/hydra-net/vanilla-lnd/tree/master/kvdb "kvdb")

[build(deps): bump golang.org/x/net from 0.4.0 to 0.7.0 in /kvdb](/hydra-net/vanilla-lnd/commit/ded9fb87d256f59258c1e08390f77c71ebeab9d1 "build(deps): bump golang.org/x/net from 0.4.0 to 0.7.0 in /kvdb
Bumps [golang.org/x/net](https://github.com/golang/net) from 0.4.0 to 0.7.0.
- [Release notes](https://github.com/golang/net/releases)
- [Commits](https://github.com/golang/net/compare/v0.4.0...v0.7.0)
---
updated-dependencies:
- dependency-name: golang.org/x/net
dependency-type: direct:production
...
Signed-off-by: dependabot[bot] <support@github.com>")

February 17, 2023 16:03

[labels](/hydra-net/vanilla-lnd/tree/master/labels "labels")

[multi: fix `make fmt`](/hydra-net/vanilla-lnd/commit/0735522194a820b76d7d2d358ee8b792daf1e356 "multi: fix `make fmt`")

August 23, 2022 22:10

[lncfg](/hydra-net/vanilla-lnd/tree/master/lncfg "lncfg")

[multi: add new build tag `integration`](/hydra-net/vanilla-lnd/commit/edba93899647afde968e09690bd557d19722e5d0 "multi: add new build tag `integration`
This commit adds a new build tag `integration` and removes the old tag
`rpctest` for clarity. Multiple unnecessary usages of `build !rpctest`
is also removed.")

February 23, 2023 21:56

[lnencrypt](/hydra-net/vanilla-lnd/tree/master/lnencrypt "lnencrypt")

[lnencrypt: Moves the crypto functions in the chanbackup package into …](/hydra-net/vanilla-lnd/commit/e0fc5bb234c12d3418f242508a15f2f06c33ceac "lnencrypt: Moves the crypto functions in the chanbackup package into its own package called lnencrypt
The functions inside of the crypto.go file in chanbackup (like EncryptPayloadToWriter and DecryptPayloadFromReader) can be used by a lot of things outside of just the chanbackup package. We can't just reference them directly from the chanbackup package because it's likely that it would generate circular dependencies. Therefore we need to move these functions into their own package to be referenced by chanbackup and whatever new functionality that needs them")

September 30, 2022 01:53

[lnmock](/hydra-net/vanilla-lnd/tree/master/lnmock "lnmock")

[lnmock: add new package `lnmock` to host mocks](/hydra-net/vanilla-lnd/commit/5e6f10c9b857f4e9027f48df0f4fa74f4b3f189d "lnmock: add new package `lnmock` to host mocks
This commit introduces a new package to host mocked objects that can be
used for all the unit tests.")

January 12, 2023 22:08

[lnpeer](/hydra-net/vanilla-lnd/tree/master/lnpeer "lnpeer")

[multi: use btcd's btcec/v2 and btcutil modules](/hydra-net/vanilla-lnd/commit/7dfe4018ce2f95c2f6a9ff04e370f668fc755138 "multi: use btcd's btcec/v2 and btcutil modules
This commit was previously split into the following parts to ease
review:
- 2d746f68: replace imports
- 4008f0fd: use ecdsa.Signature
- 849e33d1: remove btcec.S256()
- b8f6ebbd: use v2 library correctly
- fa80bca9: bump go modules")

March 9, 2022 19:02

[lnrpc](/hydra-net/vanilla-lnd/tree/master/lnrpc "lnrpc")

[Merge pull request](/hydra-net/vanilla-lnd/commit/54a1661c45bf5486ca52badfe9ee6a33a6875b29 "Merge pull request #7451 from CRex15/walletkit+labeltransaction
Add note to LabelTransaction [skip ci]") [lightningnetwork#7451](https://github.com/lightningnetwork/lnd/pull/7451) [from CRex15/walletkit+labelt…](/hydra-net/vanilla-lnd/commit/54a1661c45bf5486ca52badfe9ee6a33a6875b29 "Merge pull request #7451 from CRex15/walletkit+labeltransaction
Add note to LabelTransaction [skip ci]")

March 6, 2023 18:54

[lntest](/hydra-net/vanilla-lnd/tree/master/lntest "lntest")

[lntest: use trace log level for discovery](/hydra-net/vanilla-lnd/commit/b8373f5628f0f5a2767d1ce24fbcab08ca61b4ca "lntest: use trace log level for discovery")

March 8, 2023 21:03

[lntypes](/hydra-net/vanilla-lnd/tree/master/lntypes "lntypes")

[lntypes+routing: add generic Min/Max functions](/hydra-net/vanilla-lnd/commit/99273cc5e1a96c01a66a657043008e25792da626 "lntypes+routing: add generic Min/Max functions")

December 12, 2022 13:22

[lnutils](/hydra-net/vanilla-lnd/tree/master/lnutils "lnutils")

[multi: make linter happy](/hydra-net/vanilla-lnd/commit/4a0a15586b28f5e82bf4977fe77855558a152b7d "multi: make linter happy
Fix all the linter problems for the `v0.16.0-beta.rc3`.")

March 11, 2023 23:29

[lnwallet](/hydra-net/vanilla-lnd/tree/master/lnwallet "lnwallet")

[multi: make linter happy](/hydra-net/vanilla-lnd/commit/4a0a15586b28f5e82bf4977fe77855558a152b7d "multi: make linter happy
Fix all the linter problems for the `v0.16.0-beta.rc3`.")

March 11, 2023 23:29

[lnwire](/hydra-net/vanilla-lnd/tree/master/lnwire "lnwire")

[multi: rename due to required maxHTLC bit](/hydra-net/vanilla-lnd/commit/dd5273c88c684179b6475e26b5cc7a0a2f15ad49 "multi: rename due to required maxHTLC bit
We rename `ChanUpdateOptionMaxHtlc` to `ChanUpdateRequiredMaxHtlc`
as with the latest changes it is now required.
Similarly, rename `validateOptionalFields` to
`ValidateChannelUpdateFields`, export it to use it in a later commit.")

February 21, 2023 11:10

[macaroons](/hydra-net/vanilla-lnd/tree/master/macaroons "macaroons")

[multi: add new build tag `integration`](/hydra-net/vanilla-lnd/commit/edba93899647afde968e09690bd557d19722e5d0 "multi: add new build tag `integration`
This commit adds a new build tag `integration` and removes the old tag
`rpctest` for clarity. Multiple unnecessary usages of `build !rpctest`
is also removed.")

February 23, 2023 21:56

[make](/hydra-net/vanilla-lnd/tree/master/make "make")

[build: bump min Go version to 1.19](/hydra-net/vanilla-lnd/commit/0bbbd9b911e4fd501a18b7f699f53e104e63f3d1 "build: bump min Go version to 1.19
Fixes https://github.com/lightningnetwork/lnd/issues/7495")

March 8, 2023 18:02

[mobile](/hydra-net/vanilla-lnd/tree/master/mobile "mobile")

[docs: remove $ from multiline commands or frequently copied [skip ci]](/hydra-net/vanilla-lnd/commit/04a116093957afaedf36ea46364fc976ab2a686f "docs: remove $ from multiline commands or frequently copied [skip ci]")

October 28, 2022 12:32

[monitoring](/hydra-net/vanilla-lnd/tree/master/monitoring "monitoring")

[Merge pull request](/hydra-net/vanilla-lnd/commit/9a50cc95b7664b52c6324e65b49d9589801b7f03 "Merge pull request #6224 from Roasbeef/prometheus-latency-histograms
monitoring+cfg: add new option to export gRPC perf metrics") [lightningnetwork#6224](https://github.com/lightningnetwork/lnd/pull/6224) [from Roasbeef/prometheus-lat…](/hydra-net/vanilla-lnd/commit/9a50cc95b7664b52c6324e65b49d9589801b7f03 "Merge pull request #6224 from Roasbeef/prometheus-latency-histograms
monitoring+cfg: add new option to export gRPC perf metrics")

February 16, 2022 16:38

[multimutex](/hydra-net/vanilla-lnd/tree/master/multimutex "multimutex")

[multimutex: add hash mutex](/hydra-net/vanilla-lnd/commit/5bebda8c5df7ae41c38b89e32224fb83579abd43 "multimutex: add hash mutex")

April 8, 2020 08:54

[nat](/hydra-net/vanilla-lnd/tree/master/nat "nat")

[multi: Fix typos [skip ci]](/hydra-net/vanilla-lnd/commit/530a2059e5bc9f144aba186c53852f0ad42ed232 "multi: Fix typos [skip ci]")

January 24, 2022 12:19

[netann](/hydra-net/vanilla-lnd/tree/master/netann "netann")

[multi: enhance loggings and fix logging format](/hydra-net/vanilla-lnd/commit/6618ab493aa6298a936c341257b98fbed5d89799 "multi: enhance loggings and fix logging format
Also adds TODO for a possible bug.")

February 23, 2023 21:56

[peer](/hydra-net/vanilla-lnd/tree/master/peer "peer")

[multi: enhance loggings and fix logging format](/hydra-net/vanilla-lnd/commit/6618ab493aa6298a936c341257b98fbed5d89799 "multi: enhance loggings and fix logging format
Also adds TODO for a possible bug.")

February 23, 2023 21:56

[peernotifier](/hydra-net/vanilla-lnd/tree/master/peernotifier "peernotifier")

[multi: add shutdown logs in subservers](/hydra-net/vanilla-lnd/commit/3204e2d74b8c677e75e84cd6b8b65e9f0a49c7bf "multi: add shutdown logs in subservers
This commit adds a simple shutdown to every subserver to assist
debugging.")

September 15, 2021 19:52

[pool](/hydra-net/vanilla-lnd/tree/master/pool "pool")

[pool: replace defer cleanup with `t.Cleanup`](/hydra-net/vanilla-lnd/commit/5e6690107e765152bdaf4afaeb914dac256d0caa "pool: replace defer cleanup with `t.Cleanup`
Signed-off-by: Eng Zer Jun <engzerjun@gmail.com>")

October 13, 2022 17:47

[queue](/hydra-net/vanilla-lnd/tree/master/queue "queue")

[queue: replace defer cleanup with `t.Cleanup`](/hydra-net/vanilla-lnd/commit/7070be52b7f20ddde35570168c6bb48f6a5ebac9 "queue: replace defer cleanup with `t.Cleanup`
Signed-off-by: Eng Zer Jun <engzerjun@gmail.com>")

October 13, 2022 17:47

[record](/hydra-net/vanilla-lnd/tree/master/record "record")

[routing+channeldb: send payment metadata from invoice](/hydra-net/vanilla-lnd/commit/9195f29e61eae96dcab0bcbd0481b3fdf0c8e439 "routing+channeldb: send payment metadata from invoice")

April 13, 2022 22:55

[routing](/hydra-net/vanilla-lnd/tree/master/routing "routing")

[routing: trace capacity in probability log](/hydra-net/vanilla-lnd/commit/26d1f427dfa733edc0ee1e058fec1ccd4d609a27 "routing: trace capacity in probability log")

February 24, 2023 15:28

[rpcperms](/hydra-net/vanilla-lnd/tree/master/rpcperms "rpcperms")

[multi: improve readability of goroutine defers](/hydra-net/vanilla-lnd/commit/55b53555e93d30ad1c1ef5a841650287f99aea44 "multi: improve readability of goroutine defers
This commit fixes the readability of some of the defer calls in
goroutines by making sure the defer stands out properly.")

November 21, 2022 13:54

[scripts](/hydra-net/vanilla-lnd/tree/master/scripts "scripts")

[itest: remove unused flag `goroutineDump`](/hydra-net/vanilla-lnd/commit/d7307978806391b9b1f342a128f9167674dd2453 "itest: remove unused flag `goroutineDump`")

February 23, 2023 21:56

[shachain](/hydra-net/vanilla-lnd/tree/master/shachain "shachain")

[multi: fix `make fmt`](/hydra-net/vanilla-lnd/commit/0735522194a820b76d7d2d358ee8b792daf1e356 "multi: fix `make fmt`")

August 23, 2022 22:10

[signal](/hydra-net/vanilla-lnd/tree/master/signal "signal")

[multi: Update Licenses to 2022 [skip ci]](/hydra-net/vanilla-lnd/commit/62dc1b5323dbf12175146899bb55dfe507a77cd3 "multi: Update Licenses to 2022 [skip ci]")

February 9, 2022 00:25

[subscribe](/hydra-net/vanilla-lnd/tree/master/subscribe "subscribe")

[multi: add interface for subscribe client so it can be mocked](/hydra-net/vanilla-lnd/commit/3aa008ab043856e39e66b2248084847c5d678132 "multi: add interface for subscribe client so it can be mocked
The current implementation of subscribe is difficult to mock because
the queue that we send updates on in unexported, so you cannot create
a subscribe.Client object and then add your own updates. While it is
possible to run a subscribe server in tests, subscribe servers will
shutdown before dispatching their udpates to all clients, which can be
flakey (and is difficult to workaround). In this commit, we add a
subscription interface so that these testing struggles can be addressed
with a mock.")

September 8, 2020 13:47

[sweep](/hydra-net/vanilla-lnd/tree/master/sweep "sweep")

[multi: add new build tag `integration`](/hydra-net/vanilla-lnd/commit/edba93899647afde968e09690bd557d19722e5d0 "multi: add new build tag `integration`
This commit adds a new build tag `integration` and removes the old tag
`rpctest` for clarity. Multiple unnecessary usages of `build !rpctest`
is also removed.")

February 23, 2023 21:56

[ticker](/hydra-net/vanilla-lnd/tree/master/ticker "ticker")

[multi: improve readability of goroutine defers](/hydra-net/vanilla-lnd/commit/55b53555e93d30ad1c1ef5a841650287f99aea44 "multi: improve readability of goroutine defers
This commit fixes the readability of some of the defer calls in
goroutines by making sure the defer stands out properly.")

November 21, 2022 13:54

[tlv](/hydra-net/vanilla-lnd/tree/master/tlv "tlv")

[multi: update to latest version of btcd in submodules](/hydra-net/vanilla-lnd/commit/d61e668f561050d73f04edb8d03c58e7be26d7dc "multi: update to latest version of btcd in submodules
The main package has already been updated, but here we update the
submodules as well that only import things to use a constant or so here
and there.")

November 16, 2022 17:50

[tools](/hydra-net/vanilla-lnd/tree/master/tools "tools")

[ci: fix lint VSC permissions error](/hydra-net/vanilla-lnd/commit/22c1605687812e1b934416d3e8740ecdf3254536 "ci: fix lint VSC permissions error")

February 1, 2023 01:00

[tor](/hydra-net/vanilla-lnd/tree/master/tor "tor")

[build(deps): bump golang.org/x/net in /tor](/hydra-net/vanilla-lnd/commit/534535f8dbbfc1b6014426f3039db2758b7dd813 "build(deps): bump golang.org/x/net in /tor
Bumps [golang.org/x/net](https://github.com/golang/net) from 0.0.0-20211015210444-4f30a5c0130f to 0.7.0.
- [Release notes](https://github.com/golang/net/releases)
- [Commits](https://github.com/golang/net/commits/v0.7.0)
---
updated-dependencies:
- dependency-name: golang.org/x/net
dependency-type: direct:production
...
Signed-off-by: dependabot[bot] <support@github.com>")

March 3, 2023 09:15

[walletunlocker](/hydra-net/vanilla-lnd/tree/master/walletunlocker "walletunlocker")

[walletunlocker: fix unit test flake by closing DB](/hydra-net/vanilla-lnd/commit/2086f09489d7cb6fb74a28409aaaf638e5a753b9 "walletunlocker: fix unit test flake by closing DB
This fixes a unit test flake that occurred sometimes if the temporary
directory was attempted to be deleted but the wallet or macaroon DB
hasn't been closed yet.
