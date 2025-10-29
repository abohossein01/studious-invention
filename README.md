Welcome to PlayHT

The PlayHT API provides a simple interface to our state-of-the-art AI TTS models. Follow this guide to get started.

1. Create authentication credentials
Generate a user ID and API key in the dashboard.

2. Install the SDK (optional)
npm
pnpm
yarn
pip

npm install playht
3. Make your first request
Node.js
cURL

import * as PlayHT from 'playht';
import fs from 'fs';

// Initialize client
PlayHT.init({
  userId: '<YOUR_USER_ID>',
  apiKey: '<YOUR_API_KEY>',
});

async function streamAudio(text) {
  const stream = await PlayHT.stream('All human wisdom is summed up in these two words: Wait and hope.', { voiceEngine: 'PlayDialog' });
  stream.on('data', (chunk) => {
    // Do whatever you want with the stream, you could save it to a file, stream it in realtime to the browser or app, or to a telephony system
    fs.appendFileSync('output.mp3', chunk);
  });
  return stream;
}
4. Learn more
Input Streaming with LLMs
Our API supports Input streaming to make it seamless to integrate with LLMs like chatGPT, check this guide to see an example of how to use it.

Techniques to guarantee the lowest latency
Check this guide for some techniques to keep in mind when trying to achieve the lowest latency.

Audio streaming with Twilio
Follow this guide for integrating realtime audio streaming with Twilio for over the phone conversations.

Instant Voice Cloning
You can clone any voice instantly across languages with only 30 seconds of speech, try it easily in our API Playground, or through the API here.
