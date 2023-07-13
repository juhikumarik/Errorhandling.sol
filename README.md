# Errorhandling.sol
juhiToken Contract

Contract Details
The contract contains the following variables and functions:

uint public num = 0: A public unsigned integer variable named num with an initial value of 0.
uint b = 10: An unsigned integer variable named b with a value of 10.
testAssert(uint num)
The testAssert function is a pure function that takes a parameter num. It uses the assert statement to validate that num is not equal to zero. If the condition is not met, it will throw an exception.

divide(uint _numerator, uint _denomenator)
The divide function is a pure function that takes two parameters: _numerator and _denominator. It performs a division operation on _numerator and _denominator. However, before performing the division, it checks if _numerator is less than _denominator. If this condition is true, it reverts the transaction with the error message "Please provide a numerator greater than denominator." Otherwise, it returns the result of the division.

mult(uint a)
The mult function is a view function that takes a parameter a. It requires that a is greater than zero; otherwise, it throws an exception with the error message "Value of a is zero, we don't want the result to be zero." If the condition is met, it returns the result of multiplying a with the value of variable b.

// SPDX-License-Identifier: MIT
pragma solidity ^0.8.17;

contract ErrorHandling {

    // uint public num = 0;
    uint b=10;

    function testAssert(uint num) public pure{
        assert(num!=0);
    }

    function divide(uint _numerator, uint _denomenator) public pure returns (uint){
        if(_numerator<_denomenator){

            revert("please provide numerator greater than denomenator");

        }
        return _numerator/_denomenator;


    }
    function mult(uint a) public view returns (uint){
        require(a>0,"Value of a is zero , we don't want the result to be zero");
        return a*b;

    }

}

AUTHOR NAME
juhikumarik

License
This contract is licensed under the MIT License
