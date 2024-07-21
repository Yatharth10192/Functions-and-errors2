# Understanding Error Handling through a basic address manager

Understanding Error handling in Solidity using require(), assert() and revert() statements.

## Description

1. Developing a Smart Contract
2. Understanding Error Handling

## Getting Started

### Installing

* You can use a online Ethereum IDE, here in this code Remix is being used.

### Executing program

* Go to the Remix Ethereum IDE (remix.ethereum.org)
* Create a new file with any suitable name with (.sol) extension
* Write the desired code in the main screen
* Now, compile your file using solidity compiler
* After complining just deploy it get the desired output.

* Copy the following code and execute in a Ethereum IDE
1. Code for require() function.
``` Solidity
function addAddress(address _address) public onlyOwner {
        require(_address != address(0), "Invalid address");
        approvedAddresses[_address] = true;
        assert(approvedAddresses[_address] == true);
    }

```
2. Code for assert() function.
``` Solidity
 function removeAddress(address _address) public onlyOwner {
        require(_address != address(0), "Invalid address");
        require(approvedAddresses[_address], "Address not approved");
        approvedAddresses[_address] = false;
        assert(approvedAddresses[_address] == false);
    }
```

3. Code for revert() function.
``` Solidity
function isApproved(address _address) public view returns (bool) {
        if (_address == address(0)) {
            revert("Invalid address");
        }
        return approvedAddresses[_address];
    }
```

## Help

For any issue with the code take help of debug option.

### Authors

Yatharth Sharma
9350677109
