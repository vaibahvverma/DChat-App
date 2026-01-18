# Chat-dApp
Chat dApp on Avalanche using Solidity and ReactJS

A decentralized Chat Application on Avalanche's Fuji test-network.The dApp will allow users to connect with other people and chat with them.Smart contract using Solidity which will be deployed on Avalanche's C-chain And Easy-to-use UI developed using ReactJS.

# What is Avalanche(Avalanche Consensus Simply Explained here https://youtu.be/3TAgLJHTYRg) and Why Avalanche?
 
 Avalanche is an open-source platform for launching decentralized finance applications and enterprise blockchain deployments in one interoperable, highly scalable  ecosystem.
 Developers who build on Avalanche can easily create powerful, reliable, and secure applications and custom blockchain networks with complex rulesets or build on existing private or public subnets.

 Avalanche's Primary Network is a subnet that has three chains: P-Chain, X-Chain, and C-Chain.
 The C-Chain is an instance of the Ethereum Virtual Machine powered by Avalanche’s Snowman consensus protocol.
 The C-Chain RPC can do anything a typical Ethereum client can by using the Ethereum-standard RPC calls.
 The immediate benefits of using the C-Chain rather than Ethereum are all of the benefits of using Avalanche.
 These properties that could considerably improve the performance of DApps and the user experience.

# To build the same:-
 # Prerequisites
 Basic familiarity with Reactjs and Solidity
 Know the working of Or have Deployed a Smart Contract on Avalanche using Remix and MetaMask
 
 # Requirements:-
 Node.js v10.18.0+ And Metamask extension on your browser
 
# Smart Contract
Basic functionality of our Chat dApp is allowing users to connect with and share messages with friends.
 # To accomplish this, we will write the functions responsible for creating an account, adding friends and sending messages.
 
 # Account creation
  We will define 3 functions :
  
  ->The checkUserExists(pubkey) function is used to check if a user is registered with our application or not. It will help make sure duplicate users are not created and it will also be called from other functions to check their existence.
  ->The createAccount(username) function registers a new user on the platform with the provided username.
  ->The getUsername(pubkey) function will return the username of the given user if it exists.

  # Adding friends
  Here also we will define 3 functions :
  
  ->The checkAlreadyFriends(pubkey1, pubkey2) function checks whether two users are already friends with each other or not. This is needed to prevent duplicate channel between the same parties and will also be used to prevent a user from sending messages to other users unless they are friends.
  ->The addFriend(pubkey, name) function mark the two users as friend if they both are registered on the platform and are already not friends with each other.
  ->The getMyFriendList() function will return an array of friends of the given user.

  # Messaging
  The final part of the Solidity contract will enable the exchange of messages between users. We will divide the task into two functions sendMessage() and readMessage().
  
  ->The sendMessage() function allows a user to send messages to another registered user (friend). This is done with checkUserExists(pubkey) and checkAlreadyFriends(pubkey1, pubkey2).
  ->The readMessage() function returns the chat history that has happened between the two users so far.

  # User Data Collections
  
  We will have three types of user-defined data :
  
  ->user will have the properties name which stores the username, and friendList which is an array of other users.
  ->friend will have the properties pubkey which is the friends' public address, and name which the user would like to refer them as.
  ->message has three properties: sender, timestamp and msg, which is short for "message".
  
  We would maintain 2 collections in our database:
  
  ->userList where all the users on the platform are mapped with their public address.
  ->allMessages stores the messages. As Solidity does not allow user-defined keys in a mapping, we can instead hash the public keys of the two users. This value can then be stored in the mapping.
  
# Result
x-special/nautilus-clipboard
copy
file:///home/dungexn/Pictures/Screenshot%20from%202021-06-30%2012-01-00.png
![Screenshot from 2021-06-30 12-01-00](https://user-images.githubusercontent.com/75042859/123912946-44102880-d99b-11eb-8960-8fb575b14601.png)

# Make Sure Of:-
 ->your account has sufficient balance at fuji block-explorer.
 ->you have selected the correct account on metamask if you have more than one account connected to the site.
 ->doublecheck that you have updated the CONTRACT_ADDRESS variable in src/index.js.

# Updates:-
This dApp has very limited functionality. Improvement can be done by adding functions to delete messages, block users, or create groups of friends.
We could also optimize the dApp interaction cost with functions to limit the maximum number of messages, or possibly using event log for short messages.

