# Azure Active Directory Sample REST API Service for Node.js using MongoDB and Restify
| [Getting Started](https://docs.microsoft.com/en-us/azure/active-directory/develop/active-directory-v2-devquickstarts-node-api) | [Library](https://github.com/AzureAD/passport-azure-ad) | [Docs](https://aka.ms/aadv2) | [Support](README.md#community-help-and-support) | [Protocol](https://docs.microsoft.com/en-us/azure/active-directory/develop/active-directory-v2-protocols)
| --- | --- | --- | --- | --- |

This Node.js server will give you a quick and easy way to set up a REST API Service. Then this service is integrated with Azure Active Directory for API protection using the OAuth2 protocol. The sample server included in the download is designed to run on any platform.

This REST API server is built using Restify and MongoDB with the following features:

* A node.js server running a REST API interface with JSON using MongoDB as persistent storage
* REST APIs leveraging OAuth2 protocol for API protection using Microsoft Azure Active Directory


## Prerequisites

To run this sample you will need the following:

* Either a [Microsoft account](https://www.outlook.com) or [Office 365 for business account](https://msdn.microsoft.com/en-us/office/office365/howto/setup-development-environment#bk_Office365Account)

* Install Node.js from http://nodejs.org/

* Install MongoDB from [MongoDB download center ](https://www.mongodb.com/download-center?_ga=2.51199855.799714080.1524437300-1146184949.1522821734#production). Make sure to add the location of the MongoDB server to your environment PATH and run the MongoDB server.

**NOTE:** This walkthrough assumes that you use the default installation and server endpoints for MongoDB, which at the time of this writing is: mongodb://localhost. This should work locally without any configuration changes if you run this sample on the same machine as you've installed and ran mongodb.


## Register your Web API

Create a new app at [apps.dev.microsoft.com](https://apps.dev.microsoft.com), or follow these [detailed steps](https://azure.microsoft.com/en-us/documentation/articles/active-directory-v2-app-registration/).  Make sure to:

- Copy down the **Application Id** assigned to your app, you'll need it soon.
- Add the **Web** platform for your app.
- Enter the correct **Redirect URI**. The redirect uri indicates to Azure AD where authentication responses should be directed - the default for this sample is `http://localhost:3000`.

## Download the Sample application and modules

Next, clone the sample repo and install the NPM.

From your shell or command line:

```
$ git clone git@github.com:AzureADQuickStarts/AppModelv2-WebAPI-nodejs.git
$ cd node-server
$ npm install
```

## Configure your server using config.js

Please update the `exports.creds` and `exports.mongoose_auth_local` in config.js as instructed.
* Update `<tenant_name>` in `exports.identityMetadata` with the Azure AD tenant name of the format \*.onmicrosoft.com.
* Update `exports.clientID` with the Application Id noted from app registration.

## Run the application

```
$ cd node-server
$ node app.js
```

**Is the server output hard to understand?:** We use `bunyan` for logging in this sample. The console won't make much sense to you unless you also install bunyan and run the server like above but pipe it through the bunyan binary:

```
$ node server.js | bunyan
```

## You're done!

You will have a server successfully running on `http://localhost:3000`. Your REST / JSON API Endpoint will be available at `http://localhost:3000/api/tasks`. It will return 'unauthorized' when visited without a valid OAuth bearer token.


## Community Help and Support

We use [Stack Overflow](http://stackoverflow.com/questions/tagged/azure-active-directory) with the community to provide support. We highly recommend you ask your questions on Stack Overflow first and browse existing issues to see if someone has asked your question before. Make sure that your questions or comments are tagged with [azure-active-directory].

If you find a bug or issue with this sample, please raise the issue on [GitHub Issues](../../issues).

For issues with the passport-azure-ad library, please raise the issue on the library GitHub repo.

## Contributing

If you'd like to contribute to this sample, please follow the [GitHub Fork and Pull request model](https://help.github.com/articles/fork-a-repo/).

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/). For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.   

## Security Library

This library controls how users sign-in and access services. We recommend you always take the latest version of our library in your app when possible.

## Security Reporting

If you find a security issue with our libraries or services please report it to [secure@microsoft.com](mailto:secure@microsoft.com) with as much detail as possible. Your submission may be eligible for a bounty through the [Microsoft Bounty](http://aka.ms/bugbounty) program. Please do not post security issues to GitHub Issues or any other public site. We will contact you shortly upon receiving the information. We encourage you to get notifications of when security incidents occur by visiting [this page](https://technet.microsoft.com/en-us/security/dd252948) and subscribing to Security Advisory Alerts.

Copyright (c) Microsoft Corporation.  All rights reserved. Licensed under the MIT License (the "License");

## Acknowledgements

We would like to acknowledge the folks who own/contribute to the following projects for their support of Microsoft Azure Active Directory and their libraries that were used to build this sample. In places where we forked these libraries to add additional functionality, we ensured that the chain of forking remains intact so you can navigate back to the original package. Working with such great partners in the open source community clearly illustrates what open collaboration can accomplish. Thank you!


- [MongoDB](http://www.mongodb.org) - MongoDB (from "humongous") is an open-source document database, and the leading NoSQL database. Written in C++
- [Restify](http://mcavage.me/node-restify/) - Restify is a node.js module built specifically to enable you to build correct REST web services. ``` node-restify```
- [Restify-OAuth2](https://github.com/domenic/restify-oauth2) - This package provides a very simple OAuth 2.0 endpoint for the Restify framework. ``` restify-oauth2```
- [node-jwt-simple](https://github.com/hokaccha/node-jwt-simple) - Library for parsing JSON Web Tokens (JWT) ```node-jwt-simple```
- [http-bearer-strategy](https://github.com/jaredhanson/passport-http-bearer) - HTTP Bearer authentication strategy for Passport and Node.js.
