# Live Transcribing Multiple Phone Calls Silmultaneously using Twilio Media Streams and Google Speech-to-Text

With Twilio Media Streams, you can extend the capabilities of your Twilio-powered voice application with real time access to the raw audio stream of phone calls.

This demo follows on from my previous demo showing you how to get started with Twilio Media Streams and live transcription. If you haven’t set up a live call transcription before, I recommend getting [my other demo working first](https://github.com/nokenwa/twilio-media-stream-live-transcription-node). In this demo, I have altered the application to be able to handle multiple phone calls at the same time. It is able to monitor the transcribed speech from multiple phone calls, live in the browser using Twilio and Google Speech-to-Text with Node.js.

## Blog Post

If you prefer a step by step guide through building this yourself, this blog post will guide you through transcribing speech from a phone call into text, live in the browser using Twilio and Google Speech-to-Text using Node.js.

[Visit the Blog Post here](LINK TO BE ADDED)

---

## Prerequisites

Before we can get started, you’ll need to make sure to have:

- A [Free Twilio Account](https://www.twilio.com/try-twilio)
- A [Google Cloud Account](https://cloud.google.com/)
- Installed [ngrok](https://ngrok.com/)
- Installed the [Twilio CLI](https://www.twilio.com/docs/twilio-cli/quickstart)

---

## Setup

1.  Setup Google Project and retrieve service account key

    a. [Install and initialize the Cloud SDK](https://cloud.google.com/sdk/docs/)

    b. Setup a new GCP Project

    c. Enable the Google Speech-To-Text API for that project

    d. Create a service account.

    e. Download a private key as JSON.

2.  Modify the `.env.sample` file to include the path to your JSON service account key and save it as a `.env` file
3.  Run the following commands:

    Buy a Phone Number (_I have used the `GB` country code to buy a mobile number, but feel free to change this for a [number local to you](https://support.twilio.com/hc/en-us/articles/223183068-Twilio-international-phone-number-availability-and-their-capabilities)._)

    `$ twilio phone-numbers:buy:mobile --country-code GB`

    Start ngrok:

    `$ ngrok http 8080`

    While this is running in a new window copy the forwarding HTTPS URL (https://xxxxx.ngrok.io) and set your Twilio number to this URL:

    `$ twilio phone-numbers:update TWILIO_NUMBER --voice-url https://xxxxxxxx.ngrok.io`

    Install dependencies and start your server:

    `$ npm install`

    `$ npm start`

---

# Contact me

If you have any questions, feedback or just want to show me what you build, feel free to reach out to me:

- Twitter: [@chatterboxcoder](https://twitter.com/chatterboxCoder)
- GitHub: nokenwa
- Email: nokenwa@twilio.com
