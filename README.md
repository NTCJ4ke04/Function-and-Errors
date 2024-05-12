# Function-and-Errors
git@github.com:NTCJ4ke04/Function-and-Errors.git
// SPDX-License-Identifier: MIT
pragma solidity  >0.8.0;

contract ErrorHandling {
    address public owner;
    uint public value;

    constructor(){
        owner = msg.sender;
        value = 100; //Initial value
    }

    function changeValue(uint _newValue) public {
        require(msg.sender == owner,  "Owner can change the value");
        value = _newValue;
    }

    function assertExample(uint _num) public pure returns (uint) {
        assert(_num >0);
        return _num;
    }

    function revertExample(uint _num) public pure returns (uint) {
        require(_num != 0, "Number cannot be zero");
        return _num;
    }
}
