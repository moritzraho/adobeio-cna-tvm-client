[![Version](https://img.shields.io/npm/v/@adobe/adobeio-cna-tvm-client.svg)](https://npmjs.org/package/@adobe/adobeio-cna-tvm-client)
[![Downloads/week](https://img.shields.io/npm/dw/@adobe/adobeio-cna-tvm-client.svg)](https://npmjs.org/package/@adobe/adobeio-cna-tvm-client)
[![Build Status](https://travis-ci.com/adobe/adobeio-cna-tvm-client.svg?branch=master)](https://travis-ci.com/adobe/adobeio-cna-tvm-client)
[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
[![Codecov
Coverage](https://img.shields.io/codecov/c/github/adobe/adobeio-cna-tvm-client/master.svg?style=flat-square)](https://codecov.io/gh/adobe/adobeio-cna-tvm-client/)

# Adobe I/O CNA Token Vending Machine Client

A JS client to access the token vending machine.

For the server side code see: [adobe/adobeio-cna-token-vending-machine](https://github.com/adobe/adobeio-cna-token-vending-machine)

## Install

`npm install @adobe/adobeio-cna-tvm-client`

## Use

```javascript
const TvmClient = require('@adobe/adobeio-cna-tvm-client')
const tvm = TvmClient.init({ ow: { auth: '<myauth>', namespace: '<mynamespace>' } })

// aws s3
const awsS3Credentials = await tvm.getAwsS3Credentials()
const aws = require('aws-sdk')
const s3 = new aws.S3(awsS3Credentials)
// ...operations on s3 object

// azure blob
const azureBlobCredentials = await tvm.getAzureBlobCredentials()
const azure = require('@azure/storage-blob')
const azureCreds = new azure.AnonymousCredential()
const pipeline = azure.StorageURL.newPipeline(azureCreds)
const containerURLPrivate = new azure.ContainerURL(azureBlobCredentials.sasURLPrivate, pipeline)
const containerURLPublic = new azure.ContainerURL(azureBlobCredentials.sasURLPublic, pipeline)
// ...operations on containerURLPrivate and containerURLPublic
```

## Explore

`goto` [API](doc/api.md)

## Contributing

Contributions are welcomed! Read the [Contributing Guide](./.github/CONTRIBUTING.md) for more information.

## Licensing

This project is licensed under the Apache V2 License. See [LICENSE](LICENSE) for more information.
