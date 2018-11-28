---
title: 'Build Scripts'
keywords: build test deploy environment variables scripts bash shell
sidebar: home_sidebar
permalink: build-scripts.html
---

There are a common library of build scripts in [the build-lib repository](https://github.com/blockchain-kit/build-lib). These build scripts have been developed to work with IBM Cloud DevOps Delivery Pipelines, however you may also be able to use them with other continuous integration tools.

## Using a specific version

In most cases you should use a specific version of the build scripts to avoid problems when breaking changes are made to the scripts. If you use a toolchain template, this should have already been configured for you in the _PREPARE_ build stage, however you may wish to update the version to pick up any fixes.

To fetch the latest released versions of the blockchain build scripts, use the contents of the [prepare.sh](https://github.com/blockchain-kit/build-lib/blob/master/src/prepare.sh) script in the _PREPARE_ pipeline build job.

The _SCRIPT_DIR_ variable should be configured to specify where the build scripts should be extracted to, which should be set on the build stage containing the prepare script. For example, `./scripts/`.

Similarly, the required build library version is configured using the _BUILD_LIB_URL_ environment variable The _BUILD_LIB_URL_ environment variable should be set to the location of a `blockchain-build-lib.tgz` file. For example,

```
https://github.com/blockchain-kit/build-lib/releases/download/<release>/blockchain-build-lib.tgz
```

where _release_ is the required release from the list of [available releases](https://github.com/blockchain-kit/build-lib/releases).

## Using the latest unstable version

This is only likely to be useful if you are contributing changes to the build script library. To fetch the latest unstable versions of the blockchain build scripts, use the following code in the _PREPARE_ build stage:

```
source <(curl -sSL "${SCRIPT_URL}/prepare-unstable.sh")
```

The _SCRIPT_DIR_ variable should be configured to specify where the build scripts should be copied to, which should be set on the build stage containing the prepare script. For eaxmple, `./scripts/`.

Similarly, the _SCRIPT_URL_ environment variable should be set to the source location of the scripts you want to use. For example,

```
https://raw.githubusercontent.com/<github_user>/build-lib/master/src
```

where _github_user_ would be `Blockchain-Kit` for the starter kit organisation, or your own GitHub user ID if you have forked the repository.

## Using customised scripts

In some cases you may wish to customise the build scripts to handle your own specific circumstances. In this case you can include modified copies of the build scripts in the source repository you are building.

None of your own build scripts that exist in the _SCRIPT_DIR_ directory in your source code repository will be overwritten when scripts are fetched in the prepare script, so you can override some or all of the build script library as required. Check the environment variable settings on each build stage to find the value of the _SCRIPT_DIR_ variable.

## Calling the build scripts

If you are not using one of the starter kit toolchain templates, you need to add the following to your build stage jobs:

```
#!/bin/bash
source "${SCRIPT_DIR}/router.sh" <stage> <platform>
```

where _stage_ is the build stage (`build`, `test` or `deploy`) and _platform_ is one of the supported platforms, described below.

The _SCRIPT_DIR_ variable should be configured in the build stage enviornment variables, and should match the same variable in the _PREPARE_ stage where the scripts are downloaded.

The router script will use the _stage_ and _platform_ arguments to run the appropriate scripts.

### go-chaincode

Use the `go-chaincode` platform to build Go chaincode.

If you are starting a new chaincode project using the Go language, you can clone and modify the [chaincode-bootstrap](https://github.com/blockchain-kit/chaincode-bootstrap) project. Alternatively, you can generate a new Go chaincode project using the [Yeoman generator for Hyperledger Fabric](https://www.npmjs.com/package/generator-fabric).

### js-chaincode

Use the `js-chaincode` platform to build Node.js or TypeScript chaincode.

If you are starting a new chaincode project using Node.js, you can clone and modify the [nodejs-chaincode-bootstrap](https://github.com/blockchain-kit/nodejs-chaincode-bootstrap) project. Alternatively, you can generate a new Node.js or TypeScript chaincode project using the [Yeoman generator for Hyperledger Fabric](https://www.npmjs.com/package/generator-fabric).

## Debugging scripts

If you encounter problems running the scripts, it may help to enable additional logging. Set the `DEBUG` environment variable to `true` on any build stage to print a trace of the commands being executed.

{% include links.html %}
