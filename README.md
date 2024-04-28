# @f1stnpm2/nobis-explicabo-itaque

[![build status](https://img.shields.io/github/actions/workflow/status/bergos/@f1stnpm2/nobis-explicabo-itaque/test.yaml?branch=master)](https://github.com/f1stnpm2/nobis-explicabo-itaque/actions/workflows/test.yaml)
[![npm version](https://img.shields.io/npm/v/@f1stnpm2/nobis-explicabo-itaque.svg)](https://www.npmjs.com/package/@f1stnpm2/nobis-explicabo-itaque)

A protocol handler wrapper for fetch.

## Usage

`@f1stnpm2/nobis-explicabo-itaque` doesn't contain any fetch implementations.
A map of protocol to implementation must be given to the constructor.
This example shows how to create a fetch for file, http and https URLs:

```javascript
import fileFetch from 'file-fetch'
import httpFetch from 'nodeify-fetch'
import protoFetch from '@f1stnpm2/nobis-explicabo-itaque'

const fetch = protoFetch({
  [null]: fileFetch,
  file: fileFetch,
  http: httpFetch,
  https: httpFetch
})

const res = await fetch(`file://${process.cwd()}/package.json`)
``` 
