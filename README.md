Calculator.js: a node.js Demonstration Project
==============================================
An example node.js project, including tests with mocha, that behaves like
a pocket calculator.

[![Build Status](https://dev.azure.com/igniteMe/Fabrikam%20Test/_apis/build/status/housten.calculator?branchName=master)](https://dev.azure.com/igniteMe/Fabrikam%20Test/_build/latest?definitionId=2&branchName=master)

The project contains a simple node.js application that exposes REST APIs
to perform arithmetic on integers, and provides a test suite with mocha
and chai.  The `mocha-junit-reporters` package is included to provide XML
output that can be presented in a continuous integration tool like
[Azure DevOps](https://azure.com/devops).

To build, simply:

1. Runs `npm install` to install dependencies.
2. Runs `npm test` to run Mocha and execute the unit tests.

**NOTES**

To get status badges working, under organization settings in Azure Devops, go to pipelines, settings and turn off 'disable anonymous access to badges'

I had to disable the tests. I was using a self hosted agent because I didn't have a hosted one. I kept getting the error
```
Error: Cannot find module 'C:\agent\_work\1\s\node'
    at Function.Module._resolveFilename (internal/modules/cjs/loader.js:636:15)
    at Function.Module._load (internal/modules/cjs/loader.js:562:25)
    at Function.Module.runMain (internal/modules/cjs/loader.js:831:12)
    at startup (internal/bootstrap/node.js:283:19)
    at bootstrapNodeJSCore (internal/bootstrap/node.js:623:3)
```
even after copying the node folder locally. Possibly related to that the pipeline was initially set up to run on ubuntu and I am have a windows self-host agent. I am not sure what might need changing in the node files. I am thinking it could be related to environment variables or path standards. Node is in the path variable but perhaps ubuntu path variables have another name?
