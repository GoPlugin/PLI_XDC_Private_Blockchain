# XDC Private Blockchain setup steps
### 1. Infrastructure Requirement

1. Server:
    1. OS version: Ubuntu 20.04
    2. RAM       : 8Gb
    3. STORAGE   : 50Gb

### 2. Install golang

Please refer to [the install page](https://go.dev/doc/install). 
Remember to set environment variables:
 1. GOPATH=/home/ubuntu/go
 2. GOROOT=/usr/local/go

### 3. Prepare XinFin client
Untill "pr 238" is merged in XinFinOrg github, you can use this Repo.
```shell
cd ${HOME}
git clone https://github.com/GoPlugin/PLI_XDC_Private_Blockchain.git
cd ${HOME}/PLI_XDC_Private_Blockchain/XDPoSChain
make all
```

### 4. Create genesis

```shell
cd ${HOME}/PLI_XDC_Private_Blockchain/XDPoSChain/build/bin
./puppeth
```

#### 4.1 Input `XDPoS` as network name

![1678427309743](https://user-images.githubusercontent.com/7695325/224234053-c62252c0-1b1b-40fe-85d5-ea4d56341f1b.png)

```text
Please specify a network name to administer (no spaces or hyphens, please)
> XDPoS
```

#### 4.2 Input `2` to configure new genesis

![1678417051286](https://user-images.githubusercontent.com/7695325/224211908-436229c9-c658-4bdb-bb1d-8c382f217c97.png)

```text
What would you like to do? (default = stats)
 1. Show network stats
 2. Configure new genesis
 3. Track new remote server
 4. Deploy network components
> 2
```

#### 4.3 Input `3` to select XDPoS

![1678417349038](https://user-images.githubusercontent.com/7695325/224212620-eb8d1b76-5b67-4e5d-ad42-c582ca9c326e.png)

```text
Which consensus engine to use? (default = XDPoS)
 1. Ethash - proof-of-work
 2. Clique - proof-of-authority
 3. XDPoS - delegated-proof-of-stake
> 3
```

#### 4.4 Input `2` as block time

![1678418309539](https://user-images.githubusercontent.com/7695325/224214658-7f25b327-ab78-445b-b0d6-ca8e4c52265f.png)

```text
How many seconds should blocks take? (default = 2)
> 2
```

#### 4.5 Input `2000` as reward

![1678422405816](https://user-images.githubusercontent.com/7695325/224223330-16ac0cb3-5997-4b73-a836-1b7d91048194.png)

```text
How many Ethers should be rewarded to masternode? (default = 10)
> 2000
```

#### 4.6 Input an address for first masternode

![1678419469021](https://user-images.githubusercontent.com/7695325/224217262-f79f26a2-9404-4b32-90c1-807a580a8879.png)

```text
Who own the first masternodes? (mandatory)
> xdc85f33E1242d87a875301312BD4EbaEe8876517BZ
```

Here I input my address: `85f33E1242d87a875301312BD4EbaEe8876517BZ` without `xdc` prefix. (This address is from your XDCPay Wallet Account)

#### 4.7 Input three addresses for signers

![1678420337915](https://user-images.githubusercontent.com/7695325/224219125-3ee32475-a5b4-4be6-8c1a-c6fed98141b6.png)

```text
Which accounts are allowed to seal (signers)? (mandatory at least one)
> xdc757f225273eba574196ef04f6c22bcc3ec623adc
> xdc09c1a2b3c620665ebda5aefcf51b775073b3be60
> xdccfb27876e117bcee77085c984f9042f4d43ada13
> xdc
```

Here I input 3 addresses: (These addresses are from your XDCPay Wallet Account)

- 757f225273eba574196ef04f6c22bcc3ec623adc
- 09c1a2b3c620665ebda5aefcf51b775073b3be60
- cfb27876e117bcee77085c984f9042f4d43ada13

without `xdc` prefix.

#### 4.8 Input `900` as blocks per epoch

![1678421304308](https://user-images.githubusercontent.com/7695325/224221043-be7baab9-6be5-43fc-b87f-ef6f455dc709.png)

```text
How many blocks per epoch? (default = 900)
> 900
```

#### 4.9 Input `5` as gap

![1678422570325](https://user-images.githubusercontent.com/7695325/224223681-6712ca37-ded5-49bb-88d8-d71cc0372443.png)

```text
How many blocks before checkpoint need to prepare new set of masternodes? (default = 450)
> 5
```

#### 4.10 Input foundation address

![1678422746528](https://user-images.githubusercontent.com/7695325/224224073-1585c991-96a3-448c-bb28-828652c5659b.png)

```text
What is foundation wallet address? (default = xdc0000000000000000000000000000000000000068)
> xdc50a1c6bc2156499cfda614a0e9855ba1758bf321
```

Here I input my address: `50a1c6bc2156499cfda614a0e9855ba1758bf321` without `xdc` prefix. (This address is from your XDCPay Wallet Account)

#### 4.11 Input three addresses for foudation MultiSignWallet

![1678423021572](https://user-images.githubusercontent.com/7695325/224224824-0d1bc001-a78a-4df2-847e-a1d35e1ed163.png)

```text
Which accounts are allowed to confirm in Foundation MultiSignWallet?
> xdcd9ac740163cc633c05b00c589eb7c9997925511b
> xdc4fe0fb8578841584a3693c010c455fd8a056b7d2
> xdc90597dbfdef58819fae19af21d40c03e4315bb9d
> xdc
```

Here I input 3 addresses: (These addresses are from your XDCPay Wallet Account)

- d9ac740163cc633c05b00c589eb7c9997925511b
- 4fe0fb8578841584a3693c010c455fd8a056b7d2
- 90597dbfdef58819fae19af21d40c03e4315bb9d

without `xdc` prefix.

#### 4.12 Input `2` as require number

![1678423230672](https://user-images.githubusercontent.com/7695325/224225059-d4a1ec7d-8875-4bf2-b356-8140316a88ea.png)

```text
How many require for confirm tx in Foundation MultiSignWallet? (default = 2)
> 2
```

#### 4.13 Input addresses for Team MultiSignWallet

![1678423446136](https://user-images.githubusercontent.com/7695325/224225469-49019198-42f3-4409-a24d-78d2bef670f6.png)

```text
Which accounts are allowed to confirm in Team MultiSignWallet?
> xdcd9ac740163cc633c05b00c589eb7c9997925511c
> xdc4fe0fb8578841584a3693c010c455fd8a056b7d3
> xdc90597dbfdef58819fae19af21d40c03e4315bb9e
> xdc
```

Here I input 3 addresses: (These addresses are from your XDCPay Wallet Account)

- d9ac740163cc633c05b00c589eb7c9997925511c
- 4fe0fb8578841584a3693c010c455fd8a056b7d3
- 90597dbfdef58819fae19af21d40c03e4315bb9e

without `xdc` prefix.

#### 4.14 Input `2` as require number

![1678423525255](https://user-images.githubusercontent.com/7695325/224225653-7a29d025-1b1b-46bf-9605-62e10059b727.png)

```text
How many require for confirm tx in Team MultiSignWallet? (default = 2)
> 2
```

#### 4.15 Input address for swap wallet

![1678423730436](https://user-images.githubusercontent.com/7695325/224226074-a4c3f3b9-eb5f-4efe-a6b3-ffbed104ba47.png)

```text
What is swap wallet address for fund 55m XDC?
> xdc90597dbfdef58819fae19af21d40c03e4315bb9e
```

Here I input my address: `90597dbfdef58819fae19af21d40c03e4315bb9e` without `xdc` prefix.(This address is from your XDCPay Wallet Account)

#### 4.16 Input some addresses to prefund

![1678424059975](https://user-images.githubusercontent.com/7695325/224226734-2cbc20a3-6580-4683-a6bc-6f65c23f0843.png)

```text
Which accounts should be pre-funded? (advisable at least one)
> xdcd756f8cd4083c86497622c0c6193bdfe860f04ez
> xdc0801590680024aa5b4499226947276f5e327b72a
> xdc
```

Here I input some addresses: (These addresses are from your XDCPay Wallet Account)

- d756f8cd4083c86497622c0c6193bdfe860f04ez
- 0801590680024aa5b4499226947276f5e327b72a

without `xdc` prefix.

#### 4.17 Input network ID

![1678424204234](https://user-images.githubusercontent.com/7695325/224227141-4050162c-e407-4a7f-9bd8-508a5444b14b.png)

```text
Specify your chain/network ID if you want an explicit one (default = random)
> 111
```

Here I input `111`.

#### 4.18 Export the genesis file

![1678424359028](https://user-images.githubusercontent.com/7695325/224227488-3b8c98c8-98ee-4b21-943b-2b9133d59991.png)

```text
What would you like to do? (default = stats)
 1. Show network stats
 2. Manage existing genesis
 3. Track new remote server
 4. Deploy network components
> 2

 1. Modify existing fork rules
 2. Export genesis configuration
 3. Remove genesis configuration
> 2

Which file to save the genesis into? (default = XDPoS.json)
> XDPoS.json
```

- Select `2` to manage existing genesis.
- Select `2` to export genesis configuration
- Enter genesis filename: `XDPOS.json`
- Press CtrL + C to exit

The gensis file is saved to: `${HOME}/XDPoSChain/build/bin/XDPoS.json`.

#### 4.19 Modify the genesis file

Edit the genesis file `${HOME}/XDPoSChain/build/bin/XDPoS.json`, add the below line:

```text
"constantinopleBlock": 4,
```

under the line `"eip155Block": 3,` according to [issue 196](https://github.com/XinFinOrg/XDPoSChain/issues/196).

### 5. Setup bootnode

```shell
cd ${HOME}/XDPoSChain/build/bin
./bootnode -genkey bootnode.key
./bootnode -nodekey ./bootnode.key
```

![1678428141480](https://user-images.githubusercontent.com/7695325/224236113-ddd1670b-9300-4f5b-8d68-01da199e9831.png)

Copy bootnode information in above shown:

```text
enode://enode://fa88a0faf3f57a5911e287c12326f5a50adf960f4e8e0cc8ce2287ac04b49873c6bb7c144113d9fcae15f40be9c281a3404ea3cc72c29fd4556fe2e3e4ebfa8f@[127.0.0.1]:30301
```

Then press Ctrl+C to stop bootnode program.

### 6. Start the masternodes

#### 6.1 Setup Local_DPoS_Setup

```shell
cd ${HOME}/Local_DPoS_Setup
```

#### 6.2 Copy genesis and bootkey files

```shell
cp ${HOME}/XDPoSChain/build/bin/XDPoS.json ${HOME}/Local_DPoS_Setup/genesis/
cp ${HOME}/XDPoSChain/build/bin/bootnode.key ${HOME}/Local_DPoS_Setup
```

#### 6.3 Setup ENODE and private keys

Edit file `${HOME}/Local_DPoS_Setup/.env`, add 4 private keys without 0x prefix:

```text
ENODE=<ENODE_VALUE>
PRIVATE_KEY_0=<KEY_0>
PRIVATE_KEY_1=<KEY_1>
PRIVATE_KEY_2=<KEY_2>
PRIVATE_KEY_3=<KEY_3>
```

- ENODE="enode://fa88a0faf3f57a5911e287c12326f5a50adf960f4e8e0cc8ce2287ac04b49873c6bb7c144113d9fcae15f40be9c281a3404ea3cc72c29fd4556fe2e3e4ebfa8f@[127.0.0.1]:30301"
- PRIVATE_KEY_0='cc208c02f6bd1b57249dcc3bd5a13e58c8c127542e56ef016ffc3ec5154e4e81'
- PRIVATE_KEY_1='83bf7f8349688dc2b6602883c8c14ef78f017b498c3c009d5286e3b10e1c1042'
- PRIVATE_KEY_2='5f3aab8fea3a3e654eb006d5bbb552729c1d50df270b316380ad09fa75bf022a'
- PRIVATE_KEY_3='e896872d3d5958fa87ad001c5a4437f340b1a0e21d55f3be07d533c5adf9fcd8'

#### 6.4 Start private networks
Edit file `${HOME}/Local_DPoS_Setup/start-3-private-networks.sh`, edit line number 21 to include your XDPoS.json file
```shell
./start-3-private-networks.sh
```
#### 6.5 Verify private networks
Once the node starts, wait for the block number * 4 times the blocks per epoch as given under the topic 4.8

### 7. Configure XDCPay
#### 7.1 Configure the RPC, chain ID
1. Add a new Network under "Network Settings"
2. Network Name => Private Blcokchain
3. New RPC URL => http://<public_ip_address_of_server>:<port_mentioned_in_start-3-signers-networks.hs_at_line_BASE_RPC_PORT>
4. Chain ID => As given in topic 4.17


## References
IMPORTANT: XDC Private Blockchain need to have 3 or 5 signer as mentioned under "4.5" topic.
           If we try to set it up using 2 or 4 signer node then we will have brain split as logged in       
            "https://github.com/XinFinOrg/XDPoSChain/pull/238#issuecomment-1473551663"

https://medium.com/xinfin/how-to-set-up-a-private-blockchain-network-with-xdc-network-codebase-b2ee82368e83
