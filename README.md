
## Compile solidity to abi and bin

Install solc

```shell
$ brew update
$ brew upgrade
$ brew tap ethereum/ethereum
$ brew install solidity
```

Generate abi from sol to `/build` folder

```shell
$ solc --abi --bin contracts/ERC721PresetMinterPauserAutoId.sol -o build --overwrite
```

## Truffle (Local Blockchain)

```shell
$ npm i
$ npm i -g truffle
```

```shell
$ truffle compile contracts/ERC721PresetMinterPauserAutoId.sol
$ truffle develop
```

```shell
truffle(develop)> migrate

2_deploy.js
===========

   Deploying 'ERC721PresetMinterPauserAutoId'
   ------------------------------------------
   > transaction hash:    0xe293a6069916a2020b57d8ab74995bcc7489f42a1e9047f06725140918971f34
   > Blocks: 0            Seconds: 0
   > contract address:    0x24afDE22C4b65a8C1e14a80E34f56A4499ef1aEd
   > block number:        1
   > block timestamp:     1657252744
   > account:             0x14206Eefd385F04E53Fb75511239c46830ad1A85
   > balance:             99.9855433225
   > gas used:            4283460 (0x415c44)
   > gas price:           3.375 gwei
   > value sent:          0 ETH
   > total cost:          0.0144566775 ETH

   > Saving artifacts
   -------------------------------------
   > Total cost:        0.0144566775 ETH

truffle(rinkeby)> nft = await ERC721PresetMinterPauserAutoId.deployed()
undefined

truffle(develop)> await nft.mint("0x0445c33bdce670d57189158b88c0034b579f37ce")
{ tx:
   '0xd301a60dbb8ac187687f6639f200d4e6f2cfa065923092b3940330e35a26421d',
  receipt:
  ....
```

## Unity 

Install Nethereum.Generator.Console
```shell
dotnet tool install -g Nethereum.Generator.Console
```

Make sure to add the executable to $PATH

```shell
$ Nethereum.Generator.Console generate from-abi -abi ./build/ERC721PresetMinterPauserAutoId.abi -o ./unity -ns Sample.Ethereum
```
