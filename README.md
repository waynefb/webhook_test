# webhooks_test
Simple test server to receive and show webhooks received from Facebook.

## Getting Started

1. run `yarn install`
2. run `cp .env.example .env`, and then change `.env` settings
3. run `yarn run start` to start server
4. visit `localhost:3000` or `localhost:{YOUR_PORT}`
4. (optional) use ngrok or other tunnel service to expose localhost to worldwide


## Deployment

1/ Deploy to heroku

[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy)

Configure APP_SECRET, VERIFY_TOKEN under config variable settings for your project from the [Heroku developer dashboard](https://dashboard.heroku.com/apps/):
* APP_SECRET is obtained from the [Facebook developer dashboard](https://developers.facebook.com/apps/) for your app. This is needed to verify that an update came from a Facebook server.
* VERIFY_TOKEN is your "password" for setting up a webhooks subscription.

2/ Setup your webhooks subscription from the webhooks dashboard on facebook for your app.
* The URL should be your app URL and /webhooks, e.g. https://{heroku-url}/webhooks
* The verify token should be what you configured in the previous step.

3/ While it is running, it will list received webhooks updates in chronological order at https://{heroku-url}, and you can also look at heroku logs for any errors.
