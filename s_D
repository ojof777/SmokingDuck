//SPDX-License-Identifier: MIT

pragma solidity 0.8.15;

import "@openzeppelin/contracts/token/ERC1155/ERC1155.sol";

contract LouBOI is ERC1155 {

    uint256 constant smokingDukk = 0;
    uint256 constant t_lou = 1;

    uint256 constant total_s = 10000;

    mapping(bytes32 => mapping(address => uint256)) f_balance;

    mapping(address => bool) p_minters;

    constructor() ERC1155(""){
        mint_lou;
    }

    function mint_lou(address from, uint256 amt) public returns(string memory){
        require(amt == 1);
        _mint(from, t_lou, amt, "");
        return "success";
    }

    function import_forex(address from, address to, bytes32 t_name, uint256 amount) public  returns(string memory){
        require(amount < 100000);
        require(from != to);
        f_balance[t_name][msg.sender] += amount;
        return "success";

    }
    function get_balance(address u, bytes32 name) public view returns(uint256){
        return f_balance[name][u];
    }


}
