pragma solidity 0.8.18; // as you can see in 1st line i put the version of solidity I used

// So lets create a contract, i will name it MyToken
contract MyToken {

    // Declare public variables
    string public tokenName = "Deanna";
    string public tokenAbbrv = "Andrea";
//Then We declare a uint (unsigned integer)
    uint public totalSupply = 0; 

    // Declare a public mapping to store token balances for each address
    mapping(address => uint) public balance;

    // Next is we gonna create a mint or new token and assign them in specific address
    function mint(address _address, uint _value) public {
        totalSupply += _value;
        balance[_address] += _value;
    }

    // Next is we gonna create a burn for existing token from spefici address.
    function burn(address _address, uint _value) public {
        // Check if the balance of the address is greater than or equal to the value to be burned
        if (balance[_address] >= _value) {
            totalSupply -= _value;
            balance[_address] -= _value;
        }
    }
}
