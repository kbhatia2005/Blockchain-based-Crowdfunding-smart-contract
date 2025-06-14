CrowdFunding Smart Contract (Solidity)
![Chat App Screenshot](chatapp.png)
A decentralized crowdfunding smart contract built using Solidity. This smart contract enables users to contribute funds toward a campaign, get refunds if the target is not met, and allows the campaign manager to create payment requests approved by contributors.

📌 Features
Contribution System:

Contributors can donate Ether before the deadline.

Minimum contribution: 100 wei.

Each contributor’s amount is tracked.

Refund System:

If the deadline passes and the target amount is not met, contributors can get a refund.

Request & Voting System:

Only the manager can create payment requests (e.g., for work related to the project).

Contributors can vote on requests.

If more than 50% of contributors approve, funds are released to the recipient.

🔧 Contract Variables
Variable	Purpose
manager	Deployer of contract, controls requests
minimumContribution	Minimum Ether to participate
deadline	Last timestamp to contribute
target	Required amount to consider campaign successful
raisedamount	Total amount raised so far
contributors	Mapping to track each contributor's donation
requests	Mapping of spending requests by manager
numrequest	Counter for total requests

📂 Main Functions
constructor(uint _target, uint _deadline): Initializes target and deadline.

sendEth(): Allows users to send ETH and become contributors.

getContractbalance(): Returns current contract balance.

refund(): Refund contributors if deadline is passed and target is unmet.

createrequests(...): Manager creates a fund usage request.

voteRequest(uint _requestNo): Contributors vote for a specific spending request.

makePayment(uint _requestNo): Manager sends ETH if request gets >50% approval.

🧠 Smart Concepts Used
Mappings:

To store contributions per address.

To track votes per request.

Structs & Nested Mappings:

Store complex request data including vote status.

Modifiers:

onlyManager ensures that only the contract creator can perform certain actions.

🛠 Sample Use Cases
College project for crowdfunding dApp.

Demonstrates DAO-like decision making.

Explains voting-based fund release logic in a blockchain contract.

📝 Notes
Designed using Solidity >=0.6.12 <0.9.0

Current version does not use external frontend or web3, but is easily extensible.

Includes logic to avoid double voting and restrict unauthorized access.

