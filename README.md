#Azure Active Directory Sample REST API Service for Node.js using MongoDB and Restify

This Node.js server will give you with a quick and easy way to set up a REST API Service using the OAuth2 protocol. Then this service is integrated with Azure Active Directory for API protection. The sample server included in the download are designed to run on any platform.

This REST API server is built using Restify and MongoDB with the following features:

* A node.js server running an REST API interface with JSON using MongoDB as persistent storage
* REST APIs leveraging OAuth2 API protection for endpoints using Microsoft Azure Active Directory

We've released all of the source code for this example in GitHub under an Apache 2.0 license, so feel free to clone (or even better, fork!) and provide feedback on the forums.


## Quick Start

Getting started with the sample is easy. It is configured to run out of the box with minimal setup.

### Step 1: Register a Microsoft Azure AD Tenant

To use this sample you will need a Microsoft Azure Active Directory Tenant. If you're not sure what a tenant is or how you would get one, read [What is an Azure AD tenant](http://technet.microsoft.com/library/jj573650.aspx)? or [Sign up for Azure as an organization](http://azure.microsoft.com/en-us/documentation/articles/sign-up-organization/). These docs should get you started on your way to using Microsoft Azure AD.

### Step 2: Register your Web API with your Microsoft Azure AD Tenant

After you get your Microsoft Azure AD tenant, please go to [https://apps.dev.microsoft.com/](https://apps.dev.microsoft.com/). On that page, click 'Add an app'. Give it a name like 'my_webapi_v2', then click 'Create application'. On the next page, click 'Add Platform' and select 'Web', then put 'http://localhost:3000' into the 'Redirect URIs' field, and click 'save'. Copy the Application Id of your application and save it somewhere, this value is the clientID of your web api, you will use it in step 6. 

### Step 3: Download node.js for your platform
To successfully use this sample, you need a working installation of Node.js.

Install Node.js from [http://nodejs.org](http://nodejs.org).

### Step 4: Install MongoDB on to your platform

To successfully use this sample, you must have a working installation of MongoDB. We will use MongoDB to make our REST API persistent across server instances.

Install MongoDB from [http://mongodb.org](http://www.mongodb.org).

**NOTE:** This walkthrough assumes that you use the default installation and server endpoints for MongoDB, which at the time of this writing is: mongodb://localhost. This should work locally without any configuration changes if you run this sample on the same machine as you've installed and ran mongodb.


### Step 5: Download the Sample application and modules

Next, clone the sample repo and install the NPM.

From your shell or command line:

```
$ git clone git@github.com:AzureADQuickStarts/WebAPI-Bearer-NodeJS.git
$ cd node-server
$ npm install
```

### Step 6: Configure your server using config.js

Please update the `exports.creds` and `exports.mongoose_auth_local` in config.js as instructed.

### Step 7: Run the application

```
$ cd node-server
$ node app.js
```

**Is the server output hard to understand?:** We use `bunyan` for logging in this sample. The console won't make much sense to you unless you also install bunyan and run the server like above but pipe it through the bunyan binary:

```
$ node server.js | bunyan
```

### You're done!

You will have a server successfully running on `http://localhost:3000`. Your REST / JSON API Endpoint will be `http://localhost:3000/api/tasks`

### Acknowledgements

We would like to acknowledge the folks who own/contribute to the following projects for their support of Microsoft Azure Active Directory and their libraries that were used to build this sample. In places where we forked these libraries to add additional functionality, we ensured that the chain of forking remains intact so you can navigate back to the original package. Working with such great partners in the open source community clearly illustrates what open collaboration can accomplish. Thank you!


- [MongoDB](http://www.mongodb.org) - MongoDB (from "humongous") is an open-source document database, and the leading NoSQL database. Written in C++
- [Restify](http://mcavage.me/node-restify/) - Restify is a node.js module built specifically to enable you to build correct REST web services. ``` node-restify```
- [Restify-OAuth2](https://github.com/domenic/restify-oauth2) - This package provides a very simple OAuth 2.0 endpoint for the Restify framework. ``` restify-oauth2```
- [node-jwt-simple](https://github.com/hokaccha/node-jwt-simple) - Library for parsing JSON Web Tokens (JWT) ```node-jwt-simple```
- [http-bearer-strategy](https://github.com/jaredhanson/passport-http-bearer) - HTTP Bearer authentication strategy for Passport and Node.js.




## About The Code

Code hosted on GitHub under Apache 2.0 license
