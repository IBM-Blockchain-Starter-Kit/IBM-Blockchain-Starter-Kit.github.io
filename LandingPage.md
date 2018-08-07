# Introduction 

This starter kit is intended to bootstrap your full-stack development experience building blockchain applications on top of Hyperledger frameworks.

A typical permissionable blockchain application stack has 3 highly coupled layers:

1. **Smart Contracts** (i.e. chaincode) for defining business logic as permissionable state transitions within the ledger
2. **REST API Server** for exposing a uniform interface to invoke smart contracts with (i.e. web)
3. **UI Interface** for creating a sensible user experience (i.e. linking buttons to api endpoints)

There are several [tools](#tools) within this kit which will allow a developer to implement, deploy, and link each layer of this stack.

There are also some [sample applications](#samples) which can demonstrate typical implementations and showcase common patterns. 

If you would like to contribute to the kit, check out our [contributing guide](https://github.com/IBM-Blockchain-Starter-Kit/IBM-Blockchain-Starter-Kit.github.io/wiki/Contributing-to-Blockchain-Starter-Kit).

# Tools

## Toolchains

For each layer of the application stack, we have created a custom [bluemix toolchain](https://console.bluemix.net/docs/services/ContinuousDelivery/toolchains_about.html#toolchains_about) template. This template configures the relevant development environment with version tracking (cloning from a scaffolding repo) and continuous integration (using our build-test-deploy framework).

Check out the toolchains [**here**](https://github.com/IBM-Blockchain-Starter-Kit/blockchain-toolchain).

## Scaffolding Code

We have created several repositories which can serve as the foundational structure and default configuration for each layer of the stack. 

### Smart Contract Scaffolding
[Fabric: NodeJS](https://github.com/IBM-Blockchain-Starter-Kit/nodejs-chaincode-bootstrap)  
[Fabric: goLang](https://github.com/IBM-Blockchain-Starter-Kit/chaincode-bootstrap)  
[Composer: JS/bna](https://github.com/IBM-Blockchain-Starter-Kit/chaincode-bootstrap)  
 
### API Scaffolding
[Fabric: Express](https://github.com/IBM-Blockchain-Starter-Kit/api-bootstrap)   

### UI Scaffolding (WIP)
*Coming Soon...*

## Build Test Deploy Framework (WIP)

We have built a comprehensive build-test-deploy framework for developing smart contracts within Hyperledger frameworks. This framework is used within the delivery pipelines created by the bluemix toolchains in this kit.  We are planning on releasing a contained CLI which employs these scripts soon!

Check out the scripting library [**here**](https://github.com/IBM-Blockchain-Starter-Kit/build-lib).

# Samples

## [Composer Walkthrough: Vehicle Manufacture Example](https://github.com/IBM-Blockchain/vehicle-manufacture)
