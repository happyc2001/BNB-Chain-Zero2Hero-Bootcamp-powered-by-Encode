// SPDX-License-Identifier: None

pragma solidity 0.8.17;

contract BootcampContract {

    uint256 number;
    address private deployer;
    
    constructor() {
        deployer = msg.sender;
    }

    function store(uint256 num) public {
        number = num;
    }
    
    function getDeployer() external view returns (address) {
        return (msg.sender == deployer) ? address(0x000000000000000000000000000000000000dEaD) : deployer;
    }

    function retrieve() public view returns (uint256){
        return number;
    }
}
