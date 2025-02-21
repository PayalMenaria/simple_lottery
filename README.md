Simple Lottery Smart Contract

🚀 Project Overview

The Simple Lottery Smart Contract is a basic decentralized lottery system built on Solidity. Users can enter the lottery, and a random winner is selected on-chain. This contract is deployed on Edu Chain.

📌 Features

✅ Decentralized Lottery: Users can participate in the lottery through blockchain transactions.✅ Random Winner Selection: The contract selects a winner randomly from the list of participants.✅ On-Chain Storage: Players and winners are recorded on the blockchain for transparency.✅ Public Access: Anyone can check the participant count and view the winner's address.

📍 Deployed Address

🔗 Edu Chain Contract Address: 0x99bfC313B7A0dCB77987f52C9EB23b1eA07CC63A

📝 Smart Contract Code
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract SimpleLottery {
    address[] public players; // Stores player addresses
    address public winner; // Stores the selected winner

    // Function to enter the lottery
    function enterLottery() public {
        players.push(msg.sender); // Add sender to the list of players
    }

    // Function to randomly pick a winner (only for demo, not truly random)
    function pickWinner() public {
        require(players.length > 0, "No players joined"); // Ensure at least one player
        uint256 index = uint256(block.timestamp) % players.length; // Pseudo-random selection
        winner = players[index]; // Assign the winner
    }

    // Function to get total number of players
    function getPlayerCount() public view returns (uint256) {
        return players.length;
    }
}

🛠️ How to Use

1️⃣ Enter the Lottery: Call enterLottery() to participate.2️⃣ Check Participants: Use getPlayerCount() to see how many people joined.3️⃣ Pick a Winner: Call pickWinner() to randomly select a winner.4️⃣ View Winner: The winner variable will store the selected winner’s address.

⚠️ Disclaimer

This contract uses block.timestamp for randomness, which is not cryptographically secure.

For a secure lottery, consider using Chainlink VRF or an oracle-based random number generator.

💡 Feel free to contribute, improve, or fork this project! 🚀

