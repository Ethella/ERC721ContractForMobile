
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
$ solc --abi --bin contracts/Creature.sol -o build --overwrite
```

## Unity 

Install Nethereum.Generator.Console
```shell
dotnet tool install -g Nethereum.Generator.Console
```

Make sure to add the executable to $PATH

```shell
$ Nethereum.Generator.Console generate from-abi -abi ./build/Creature.abi -o ./unity -ns Sample.Ethereum
```
