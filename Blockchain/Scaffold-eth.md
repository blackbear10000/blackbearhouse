## Introduction

Scaffold-eth provides an off-the-shelf stack for rapid prototyping on Ethereum, giving developers access to state-of-the-art tools to quickly learn and ship an Ethereum-based dApp.

Scaffold-eth is not a product itself but more of a combination or stack of other great tools. It allows you to quickly build and iterate over your smart contracts and frontends.

Here are the main components:

- Solidity for writing smart contracts.
- Hardhat for running local networks, deploying and testing smart contracts.
- React for building a frontend, using many useful pre-made components and hooks.
- Ethers.js for interacting with deployed smart contracts and the frontend
- Ant for your UI. Can be easily changed to Bootstrap or some other library you prefer.

## Link

- [Doc](https://docs.scaffoldeth.io/scaffold-eth/)

## Bugs

对于使用 scaffold-eth 默认的 thegraph 部署方式，postgresql 的数据库版本会存在问题，导致 thegraph 节点无法正常启动

在 docker-compose.yml 里相应的位置，增加环境变量：

```yml
environment:
  POSTGRES_INITDB_ARGS: "-E UTF8 --locale=C"
```

https://ethereum.stackexchange.com/questions/147213/scaffold-eths-graph-node-docker-container-dies-after-a-few-seconds-complaining
