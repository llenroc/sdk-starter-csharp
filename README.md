<a href="https://www.twilio.com">
  <img src="https://static0.twilio.com/marketing/bundles/marketing/img/logos/wordmark-red.svg" alt="Twilio" width="250" />
</a>

# Twilio SDK Starter Application for C#
[![Build Status](https://travis-ci.org/TwilioDevEd/sdk-starter-csharp.svg?branch=master)](https://travis-ci.org/TwilioDevEd/sdk-starter-csharp)

This sample project demonstrates how to use Twilio APIs in a C# web
application. Once the app is up and running, check out [the home page](http://localhost:3000)
to see which demos you can run. You'll find examples for [Chat](https://www.twilio.com/chat),
[Video](https://www.twilio.com/video), [Sync](https://www.twilio.com/sync), and more.

Let's get started!

## Setup .NET Core SDK

1. Install [.NET Core](https://www.microsoft.com/net/core).

## Configure the sample application

To run the application, you'll need to gather your Twilio account credentials and configure them
in a file named `appsettings.json` in the `src/sdkstarter` directory. To create this file from an example template, do the following in your Terminal.

**Windows**
```powershell
cd src\sdkstarter
copy .\appsettings.example.json .\appsettings.json
```

**OS X or Linux**
```bash
cp appsettings.example.json appsettings.json
```

### Configure account information

Every sample in the demo requires some basic credentials from your Twilio account. Configure these first.

| Config Value  | Description |
| :-------------  |:------------- |
`TWILIO_ACCOUNT_SID` | Your primary Twilio account identifier - find this [in the console here](https://www.twilio.com/console).
`TWILIO_API_KEY` | Used to authenticate - [generate one here](https://www.twilio.com/console/dev-tools/api-keys).
`TWILIO_API_SECRET` | Used to authenticate - [just like the above, you'll get one here](https://www.twilio.com/console/dev-tools/api-keys).

#### A Note on API Keys

When you generate an API key pair at the URLs above, your API Secret will only be shown once -
make sure to save this information in a secure location, or possibly your `~/.bash_profile`.

### Configure product-specific settings

Depending on which demos you'd like to run, you'll need to configure a few more values in your
`appsettings.json` file.

| Config Value  | Product Demo | Description |
| :-------------  |:------------- |:------------- |
`TWILIO_CHAT_SERVICE_SID` | Chat | Like a database for your Chat data - [generate one in the console here](https://www.twilio.com/console/chat/services)
`TWILIO_CONFIGURATION_SID` | Video | Identifier for a set of config properties for your video application - [find yours here](https://www.twilio.com/console/video/profiles)
`TWILIO_SYNC_SERVICE_SID` | Sync (Preview) | Like a database for your Sync data - [generate one in the console here](https://www.twilio.com/console/sync/services)

### Configuring Notify

You will need to create a Notify Service through the [Twilio Console](https://www.twilio.com/console/notify/services), and add at least one credential on the [Mobile Push Credential screen](https://www.twilio.com/console/notify/credentials) (such as Apple Push Notification Service or Firebase Cloud Messaging for Android) to send notifications using Notify.

## Run The Application

### Visual Studio

Open `sdkstarter.sln` and press *F5* or click the Run button

### Windows CLI, OS X or Linux

```bash
cd src/sdkstarter
dotnet restore
dotnet run
```

Your application should now be running at [http://localhost:3000/](http://localhost:3000/). (If you are running from Visual Studio, a
random port number may be selected as opposed to 3000.)

![Home Screen](https://cloud.githubusercontent.com/assets/809856/23171215/8107bd9e-f817-11e6-94c5-2b132d798fae.png)

Check your config values, and follow the links to the demo applications!

## Running the SDK Starter Kit with ngrok

If you are going to connect to this SDK Starter Kit with a mobile app (and you should try it out!), your phone won't be able to access localhost directly. You'll need to create a publicly accessible URL using a tool like [ngrok](https://ngrok.com/) to send HTTP/HTTPS traffic to a server running on your localhost. Use HTTPS to make web connections that retrieve a Twilio access token.

```bash
ngrok http 3000
```

## Run Tests

```bash
dotnet test sdkstarter.Test/sdkstarter.Test.csproj
```
## License
MIT
