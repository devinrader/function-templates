# Airtable

This is a collection of functions that can be used to read and write Messages to and from Airtable tables.

## Pre-requisites

To use these functions you will need an Airtable account and API Key.  See the Airtable support article "[How do I get my API Key](https://support.airtable.com/hc/en-us/articles/219046777-How-do-I-get-my-API-key-)" for details.

### Environment variables

This project requires some environment variables to be set. To keep your tokens and secrets secure, make sure to not commit the `.env` file in git. When setting up the project with `twilio serverless:init ...` the Twilio CLI will create a `.gitignore` file that excludes `.env` from the version history.

In your `.env` file, set the following values:

| Variable | Description | Required |
| :------- | :---------- | :------- |
| AIRTABLE_APIKEY | Your Airtable API Key | Yes |
| AIRTABLE_BASEID | The Airtable Base ID | Yes |
| AIRTABLE_TABLENAME | The name of the specific Base table to connect to | Yes |
| MY_PHONE_NUMBER | A Twilio phone number | Only for broadcasting messages |

## Create a new project with the template

1. Install the [Twilio CLI](https://www.twilio.com/docs/twilio-cli/quickstart#install-twilio-cli)
2. Install the [serverless toolkit](https://www.twilio.com/docs/labs/serverless-toolkit/getting-started)

```shell
twilio plugins:install @twilio-labs/plugin-serverless
```

3. Initiate a new project
    
```
twilio serverless:init example --template={{name}} && cd verify-sample
```

4. Start the server with the [Twilio CLI](https://www.twilio.com/docs/twilio-cli/quickstart):

```
twilio serverless:start
```

5. Open the web page at https://localhost:3000/index.html and enter your phone number to test

ℹ️ Check the developer console and terminal for any errors, make sure you've set your environment variables.

## Deploying

Deploy your functions and assets with either of the following commands. Note: you must run these commands from inside your project folder. [More details in the docs.](https://www.twilio.com/docs/labs/serverless-toolkit)

With the [Twilio CLI](https://www.twilio.com/docs/twilio-cli/quickstart):

```
twilio serverless:deploy
```
