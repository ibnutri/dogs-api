# DogLovers API for DogLovers website
Test API for Techsylvania 2021 Ziggeo's Workshop

## Installation
1. Clone the repo.
2. Run `composer install` inside of the repo folder. This will install the [Ziggeo PHP SDK](https://github.com/Ziggeo/ZiggeoPhpSdk)

A list with all of our server side SDKs can be found [here](https://ziggeo.com/docs/sdks/server-side)

### Create config.json file

For this to work, you should create a `config.json` file with the following info

```json
 {
  "APPTOKEN": "Application Token from Ziggeo"
  "APPSECRET": "Application Private key from Ziggeo",
  "TAGS": ["dog", "dogs", "cat", "cats", "capybara", "capybaras", "whatever you need"],
  "TAGS_SCORE_THRESHOLD": 0.7
}
```

## get_dogs.php

API Endpoint to retrieve the videos list from Ziggeo. Check the file comments for more information on how we're doing it.

## webhook_catch.php

[Webhook](https://ziggeo.com/docs/api/webhooks) destination. Ziggeo provide the ability to add webhooks to list to different [events](https://ziggeo.com/docs/api/webhooks/list).

For this example, we're using webhooks to automatically moderate videos when they match one of the desired categories.
This is done by automatically listening to the `video_analysis` event after an event is processed. The `webhook_catch.php` file must be accessible from the internet for this to work.

This is not strictly necessary as you can moderate videos through Ziggeo's Dashboard too. Just remember to also tag them how you want.