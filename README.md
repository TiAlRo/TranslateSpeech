# TranslateSpeech #
This project contains
- an audio client that records audio from a microphone and sends it to the server
- a server that recognizes the incoming speech and sends the translation to interested translation clients

## Prerequisites ##

Node.js must be installed on both the audio client and the server. Google Cloud Speech-to-Text and Translation AI have to be available from the server, i.e., the credentials to access these API must be accessible from node (see Google Cloud's [Set up Application Default Credentials](https://cloud.google.com/docs/authentication/provide-credentials-adc)).

To install the server dependencies, run `npm i` in the server's directory.

## Usage ##

To start the server on Windows, type the following line into a cmd:

`set TLS_KEY_PATH=<Path to TLS Key>& set TLS_CERT_PATH=<Path to TLS Certificate>& node Server`

To start the audio client, type `node Client` into a cmd.

Translations are available via HTTPS requests to the server's port 8443 at the path `/getTranslation` (e.g., via https://localhost:8443/getTranslation) from the translation clients.

## Restrictions ##

Currently, the server is reachable from the audio client only via the URL https://localhost:8443 and speech is translated only from `de-CH` to `uk`.