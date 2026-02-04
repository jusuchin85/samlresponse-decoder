# SAML Response Decoder

A simple, client-side tool to decode and inspect SAML responses. All processing happens locally in your browser — no data is sent to any server.

## 🚀 Live Site

**[https://samlresponsedecoder.justinalex.com](https://samlresponsedecoder.justinalex.com)**

## ✨ Features

- Decode base64-encoded SAML responses
- View raw decoded XML with one-click copy
- Extract X.509 certificate details (Issuer, Subject, Validity, Signature Algorithm)
- View raw certificate in PEM format
- Display SAML assertion info (NameID, Issuer, Destination, NotBefore, AuthnInstant, NotOnOrAfter, Status)
- Show SAML attributes (displayname, email, etc.)
- Visual indicators for expired/valid timestamps
- Helpful tooltips on hover for all fields
- Dark mode with system preference detection
- 100% client-side — your data never leaves your browser

## 📖 Usage

1. Paste your base64-encoded SAML response into the text area
2. Click **Decode**
3. Review the extracted information

## 🔍 How to Capture a SAML Response

To capture a SAML response from your browser for troubleshooting:

### Chrome / Edge

1. Open Developer Tools (`F12` or `Cmd+Option+I` on Mac)
2. Go to the **Network** tab
3. Check **Preserve log**
4. Initiate the SAML login flow (e.g., sign in to the app)
5. In the Network tab, look for a POST request to a URL containing `/saml/consume` or `/acs`
6. Click on the request, go to the **Payload** tab
7. Find the `SAMLResponse` parameter and copy its value

### Firefox

1. Open Developer Tools (`F12` or `Cmd+Option+I` on Mac)
2. Go to the **Network** tab
3. Check **Persist Logs**
4. Initiate the SAML login flow
5. Look for the POST request to the ACS (Assertion Consumer Service) URL
6. Click on the request, go to the **Request** tab
7. Find and copy the `SAMLResponse` value

### Using Browser Extensions

You can also use extensions like:
- [SAML-tracer](https://addons.mozilla.org/en-US/firefox/addon/saml-tracer/) (Firefox)
- [SAML Chrome Panel](https://chrome.google.com/webstore/detail/saml-chrome-panel/paijfdbeoenhembfhkhllainmocckace) (Chrome)

For more details, see [Okta's guide on viewing SAML responses](https://support.okta.com/help/s/article/How-to-View-a-SAML-Response-in-Your-Browser-for-Troubleshooting).

## 🔒 Privacy

All decoding happens locally in your browser using JavaScript. No SAML data is transmitted to any external server.

## 📄 License

[MIT](LICENSE)