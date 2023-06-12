# Multi Wallet - Solidity smart contract

This smart contract distributes tokens that are sent into it to multiple wallets by defined share.

## Development status

Working smart contract.

## Installation

These are the installation instructions of this software for the different Linux distributions.

**IMPORTANT NOTE**: It is recommended to install this software on a clean OS installation, otherwise it may cause that other software previously installed on your server could stop working properly due to this. You are using this software at your own risk.

### Debian / Ubuntu Linux

Log in as "root" on your server and run the following commands to download the necessary dependencies and the latest version of this software from GitHub:

```console
apt update
apt -y upgrade
apt -y install curl git
curl -sL https://deb.nodesource.com/setup_18.x | sudo bash -
apt -y install nodejs
git clone https://github.com/libersoft-org/solidity-multi-wallet.git
cd solidity-multi-wallet/src
npm i
```

### CentOS / RHEL / Fedora Linux

Log in as "root" on your server and run the following commands to download the necessary dependencies and the latest version of this software from GitHub:

```console
dnf -y update
dnf -y install curl git
curl -sL https://rpm.nodesource.com/setup_18.x | bash -
dnf -y install nodejs
git clone https://github.com/libersoft-org/solidity-multi-wallet.git
cd solidity-multi-wallet/src/
npm i
```

## Deployment:

1. Create the ".secret" file and put there your wallet mnemonic phrase (24 words) - you need to have some gas on it
2. Register on etherscan.io, polygonscan.com, bscscan.com etc. (depends on which blockchain you'd like to deploy these smart contracts on) and create your new API key
3. Create a file named ".apikey_*" and add your API key on the first line of this file ("*" means block explorer name, e.g.: etherscan, polygonscan, bscscan ...)
4. Edit the "deploy.js" file and set the contract variables depending on your needs
5. Install the dependencies and run the deploy script using this command:

```console
./deploy.sh
```

6. Follow the instructions on the screen

## Usage:

- function **addWallet**
  - **parameters:** wallet address, share percentage (2 decimals)
  - **example:** addWallet(0x123456789, 5012) - adds wallet that gets 50,12% share of every token that comes into this contract

- function **send**
  - **parameters:** token address, amount
  - **example:** send(0x987654321, 10500000000000000000)
  - **note:** sends 10.5 tokens with token address 0x987654321 into this contract and it will be sent to all wallets by their defined share

- array **Wallet**
  - **parameters:** wallet address, share percentage (2 decimals)
  - **note:** lists all defined wallets and their percentage shares in this contract

## License

This software is developed as open source under [**Unlicense**](./LICENSE).

## Donations

Donations are important to support the ongoing development and maintenance of our open source projects. Your contributions help us cover costs and support our team in improving our software. We appreciate any support you can offer.

To find out how to donate our projects, please navigate here:

[![Donate](https://raw.githubusercontent.com/libersoft-org/documents/main/donate.png)](https://libersoft.org/donations)

Thank you for being a part of our projects' success!
