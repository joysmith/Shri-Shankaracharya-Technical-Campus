### General Overview of Bitcoins

- [SHA256 Hash Generator](https://passwordsgenerator.net/sha256-hash-generator/)

- [Cryptocurrency Prices by Market Cap](https://coinmarketcap.com/)

- [Block chain transaction latest block details](https://www.blockchain.com/explorer)
  click on latest block--> select any block

- [How nonce value help to generate block](https://demoblockchain.org/block)

---

<br>

- Visual block chain [click me](https://andersbrownworth.com/blockchain/hash)

- Load Remix in your browser by visiting this link: [click me](https://remix.ethereum.org/)

```sol
pragma solidity ^0.4.17;

contract Inbox {
    string public message;

    function Inbox(string initialMessage) public {
        message = initialMessage;
    }

    function setMessage(string newMessage) public {
        message = newMessage;
    }

    function getMessage() public view returns (string) {
        return message;
    }

}
```

<br>

#### Ethereum Accounts<a id='8'></a>

<img src="assets/images/8/1.png" width="500">

<img src="assets/images/8/2.png" width="500">

<img src="assets/images/8/3.png" width="500">

<img src="assets/images/8/4.png" width="500">

<img src="assets/images/8/5.png" width="500">

<br>

#### Metamask Setup and Configuration

This steps will provide instructions for setting up the Metamask extension in your browser.

1. First, install the extension for your specific browser (Chrome or Firefox recommended): [click me](https://metamask.io/download/)

2. After the extension has been installed, a modal should automatically pop up in your browser. Check the I Agree box and click the Create a new wallet button.

<img src="assets/images/7/1.png" width="500">

3. Agree or Decline the Help us improve Metamask question.

4. Create a password for your Metamask wallet and then click the Create a new wallet button.

<img src="assets/images/7/2.png" width="500">

5. Click the Secure my wallet button

6. Click the Reveal seed phrase button. Copy this 12-word mnemonic (recovery phrase) to a secure place. Then, click the Next button.

7. Use the phrase copied in the previous step to complete the Confirm Secret Recovery Phrase form. Click Confirm when finished.

8. You should get a success message. If so, click the Got it! button.

<img src="assets/images/7/3.png" width="500">

9. Click the Next button on the install is complete screen and then click Done.

10. Exit out of any advertisements and you should now be at the Metamask dashboard.

<img src="assets/images/7/4.png" width="500">

11. Click Ethereum Mainnet in the top left corner to open the Select a Network menu and toggle Show test networks to on.

<img src="assets/images/7/5.png" width="500">

12. You will need to select the Sepolia network.

<img src="assets/images/7/6.png" width="500">

13. You can now close out the setup page and interact directly with the extension in your browser. If you have the correct network selected (Sepolia), you should see an S in the top left corner of the extension window.

---

<br>

#### Getting Test Ether to Use in the Course

Before continuing to the next lab, we will need to obtain some test Ether!

Since we will be using the Sepolia Network, we will need to use a Sepolia faucet to obtain test ether.
Option #1
Ethereum Sepolia Faucet

1. Visit [click me](https://cloud.google.com/application/web3/faucet/ethereum/sepolia)

2. Enter your Metamask wallet address and click the Recieve button.

Your wallet should eventually receive .05 ether. You will only be able to request ether once a day, so, you should try to do this a few times over the span of a few days.

---
