---
title: 'Toolchain Templates'
keywords: toolchain templates delivery pipeline devops build test deploy environment variables IBM Cloud
sidebar: home_sidebar
permalink: toolchain-templates.html
---

The starter kit provides several [Toolchain Templates](https://github.com/open-toolchain/sdk/wiki/Toolchain-Templates) which can be used to create IBM DevOps [Toolchains](https://console.bluemix.net/docs/services/ContinuousDelivery/toolchains_about.html#toolchains_about) with the appropriate tools pre-configured to build and deploy IBM Blockchain Platform projects.

Each toolchain template has its own branch in the [blockchain-toolchain](https://github.com/Blockchain-Kit/blockchain-toolchain) repository. The toolchain creation page for each template will typically be opened using a button or link provided as part of an article or tutorial. The URL parameters for these are described on the [Toolchain Creation Page Parameters](https://github.com/open-toolchain/sdk/wiki/Toolchain-Creation-Page-Parameters) Wiki page.

## Smart Contract Toolchain

{% include callout.html content="Branch: <a href='https://github.com/Blockchain-Kit/blockchain-toolchain/tree/chaincode'>chaincode</a>" type="primary" %}

The smart contract toolchain can build smart contracts written in Go or Node.js, and deploy deploy them to the IBM Blockchain Platform.

Additional query parameters used by this toolchain:

| Query parameter | Description                                   | Valid values   |
| --------------- | --------------------------------------------- | -------------- |
| `platform`      | The type of project to build                  | `go` or `js`   |
| `bootstrapRepo` | The source repository of the project to build | Repository URL |

For example:

### Go chaincode

```
https://console.ng.bluemix.net/devops/setup/deploy/?repository=https://github.com/Blockchain-Kit/blockchain-toolchain&branch=chaincode&platform=go&bootstrapRepo=https://github.com/Blockchain-Kit/chaincode-bootstrap.git
```

[![Deploy To Bluemix](https://console.ng.bluemix.net/devops/graphics/create_toolchain_button.png)](https://console.ng.bluemix.net/devops/setup/deploy/?repository=https://github.com/Blockchain-Kit/blockchain-toolchain&branch=chaincode&platform=go&bootstrapRepo=https://github.com/Blockchain-Kit/chaincode-bootstrap.git)

### Node.js chaincode

```
https://console.ng.bluemix.net/devops/setup/deploy/?repository=https://github.com/Blockchain-Kit/blockchain-toolchain&branch=chaincode&platform=js&bootstrapRepo=https://github.com/Blockchain-Kit/nodejs-chaincode-bootstrap.git
```

[![Deploy To Bluemix](https://console.ng.bluemix.net/devops/graphics/create_toolchain_button.png)](https://console.ng.bluemix.net/devops/setup/deploy/?repository=https://github.com/Blockchain-Kit/blockchain-toolchain&branch=chaincode&platform=js&bootstrapRepo=https://github.com/Blockchain-Kit/nodejs-chaincode-bootstrap.git)

{% include links.html %}
