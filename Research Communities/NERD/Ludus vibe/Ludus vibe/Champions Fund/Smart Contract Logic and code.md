

The smart contract for this use case would need to handle several key functions:

1. Accepting and tracking donations from users.
2. Calculating the matching funds based on the quadratic funding formula.
3. Distributing the matched funds to the athletes.
4. Tracking the success of the athletes and calculating the return on investment.
5. Distributing the return on investment to the original investors and the matching fund entity.

Here is a simplified example of how such a contract might look in Solidity. Please note that this is a very basic example and a real implementation would need to be much more complex and secure:

```solidity
pragma solidity >=0.4.22 <0.9.0;

contract LudusChampionFunds {
    struct Athlete {
        address payable athleteAddress;
        uint256 totalDonations;
        bool isSuccessful;
    }

    mapping(address => Athlete) public athletes;
    address payable public matchingFundEntity;
    uint256 public matchingMultiplier = 2; // This would be calculated based on the quadratic funding formula

    constructor(address payable _matchingFundEntity) public {
        matchingFundEntity = _matchingFundEntity;
    }

    function donate(address athleteAddress) public payable {
        require(msg.value > 0, "Donation amount must be greater than 0");
        athletes[athleteAddress].totalDonations += msg.value;
    }

    function distributeFunds(address athleteAddress) public {
        require(athletes[athleteAddress].isSuccessful, "Athlete must be successful to distribute funds");
        uint256 matchingFunds = athletes[athleteAddress].totalDonations * matchingMultiplier;
        athletes[athleteAddress].athleteAddress.transfer(matchingFunds);
    }

    function calculateReturn(address athleteAddress) public view returns(uint256) {
        require(athletes[athleteAddress].isSuccessful, "Athlete must be successful to calculate return");
        uint256 totalInvestment = athletes[athleteAddress].totalDonations * matchingMultiplier;
        uint256 returnOnInvestment = totalInvestment * 20 / 100; // 20% return on investment
        return returnOnInvestment;
    }

    function distributeReturn(address athleteAddress) public {
        require(athletes[athleteAddress].isSuccessful, "Athlete must be successful to distribute return");
        uint256 returnOnInvestment = calculateReturn(athleteAddress);
        uint256 returnToInvestors = returnOnInvestment / 2;
        uint256 returnToMatchingFundEntity = returnOnInvestment / 2;
        athletes[athleteAddress].athleteAddress.transfer(returnToInvestors);
        matchingFundEntity.transfer(returnToMatchingFundEntity);
    }
}
```

This contract allows users to donate to athletes, distributes matching funds to successful athletes, and calculates and distributes a return on investment when an athlete is successful. The return on investment is split evenly between the original investors and the matching fund entity.