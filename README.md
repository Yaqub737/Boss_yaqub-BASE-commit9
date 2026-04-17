# Boss_yaqub-BASE-commit9
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.19;
contract FundMe {
    mapping (address => uint256) public addressToamountFunded;
    address[] public FundersAddress;
    function Fundme() public payable {
        addressToamountFunded[msg.sender] += msg.value;
        FundersAddress.push(msg.sender);
    }
    function Withdraw() public payable returns (bool success){
        for (uint256 i = 0; i < FundersAddress.length; i++ ) {
         addressToamountFunded[FundersAddress[i]];
        }
         // transfer the remaining balance to owner:
        (success,)= (msg.sender).call {value: address(this).balance} ("");
    }
}
