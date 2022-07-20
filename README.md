# Zoom Server-to-Server OAuth 

Use of this sample app is subject to our [Terms of Use](https://zoom.us/docs/en-us/zoom_api_license_and_tou.html)

This is a sample app using a Server-to-Server OAuth app Account ID, Client ID and Client Secrete to create OAuth token, used to call the Zoom API.

Follow allong with relevant Zoom Server-to-Server OAuth documentation as we set this up:

1. [Create a Server-to-Server Oauth app](https://marketplace.zoom.us/docs/guides/build/server-to-server-oauth-app)


## Setup app locally
Clone and install the app and it's dependencies. We'll be using [Express](https://www.npmjs.com/package/express) for a basic Node.js server, [dotenv](https://www.npmjs.com/package/dotenv) for our credentials, [requests](https://www.npmjs.com/package/requests) to make HTTP requests and [nodemon](https://www.npmjs.com/package/nodemon) for easier development refreshing. 

```bash
git clone (TO DO)
```

```bash
cd server-to-server-app && npm install 
```

Run server:

```bash
npm run start
``` 

### Setup dotenv
Create a .env file in which to store you access credentials (accountID, clientID and clientSecret)

```bash
touch .env
```

Copy the following into this file, which we'll add your own values to:

```
accountID=
clientID=
clientSecret=
userID=

```

> Remember: Never share or store your client credentials publicly. Your `.env` is included in the `.gitignore` file to ensure these files won't be included in a git workflow.

### Create an OAuth App on the Zoom App Marketplace

Sign in to the Zoom App Marketplace and [Create a Server-to-Server OAuth App](https://marketplace.zoom.us/develop/create?source=devdocs). 

Creating this app will generate your Account Credentials (Account ID, Client ID and Client Secret) needed to get an access token.

Copy these credentials and add them to your `.env` file.

Example:

```
accountID=012345
clientID=1234567890
clientSecret=13245678901234567890
userID=me
```

### Fill out app information.

To activate the app, we'll need to add some quick info on the app. Add in the following: 

1. *Short Description*
2. *Company Name*
3. *Developer Name*
4. *Developer Contact*


> We won't need to add any Features to our app, but if we wanted to enable [Event Subscriptions](https://marketplace.zoom.us/docs/guides/tools-resources/webhooks#event-subscriptions) through Zoom Webhooks, we'd do it here.

### Add Scopes 

OAuth is used to guarantee that an app only has access to the data you authorize. If an app does not have the required scope, the generated token will be invalid and you it wont be able to call the API. 

To request data, we'll need to add a Scope to our app. The only data we need is for a user's profile information. Click **+ Add Scopes** and add *"View all user information"* (`user:read:admin`). Click **Done** and continue on to the Activation page. Click **Activate your app**.

## Activate your app 
With our app running on `localhost:4000`, now we can go to our browser and you'll see your Zoom profile data, with a JSON object showing the response. This API request was made using an access_token specific to this app and scopes.

In your browser, you'll see your Zoom profile data, with a JSON object showing the response. This API request was made using an `access_token` specific to this app and scopes. 

## Next steps
Follow our documentation on Server-to-Server OAuth with Zoom for more information on building an app on the Zoom App Marketplace.

Happy coding!

## Need help?
If you're looking for help, try [Developer Support](https://devsupport.zoom.us) or our [Developer Forum](https://devforum.zoom.us). Priority support is also available with [Premier Developer Support](https://zoom.us/docs/en-us/developer-support-plans.html) plans.
