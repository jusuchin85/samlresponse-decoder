# SAML Response Decoder

[![pages-build-deployment](https://github.com/jusuchin85/samlresponse-decoder/actions/workflows/pages/pages-build-deployment/badge.svg?branch=main)](https://github.com/jusuchin85/samlresponse-decoder/actions/workflows/pages/pages-build-deployment)

A client-side tool to decode and inspect SAML 2.0 responses. All processing happens locally in your browser — no data is ever sent to any server.

## 🚀 Live Site

**[https://samlresponsedecoder.jusuchin85.com](https://samlresponsedecoder.jusuchin85.com)**

## ✨ Features

- **Flexible Input Decoding**: Accepts standard Base64, URL-encoded (`%2B`, `%3D`, etc.), `SAMLResponse=` form/query payloads, Base64url, raw XML, and DEFLATE-compressed (HTTP-Redirect binding) responses with full UTF-8 support
- **Raw XML Viewer**: View pretty-printed decoded XML with one-click copy to clipboard
- **X.509 Certificate Analysis**: Extract certificate details (`Issuer`, `Subject`, `Valid From`, `Valid Until`, `Signature Algorithm`) and view the raw certificate in PEM format
- **SAML Assertion Inspection**: Display `NameID Format`, `NameID Value`, `Issuer`, `Destination`, `Not Before`, `Auth Instant`, `Not On Or After`, `Session Expires` (`SessionNotOnOrAfter`), and `Status`, with automatic detection of `<EncryptedAssertion>` payloads
- **SAML Attributes**: Extract single- and multi-valued attributes (such as `groups`, `memberOf`, `email`, and `displayName`) with automatic friendly-name resolution
- **Visual Validity Indicators**: Colour-coded status indicators for valid, not-yet-valid, and expired timestamps
- **Built-in Field Reference Modals**: Interactive, keyboard-accessible **Help** modals explaining every Certificate, Assertion, and Attribute field
- **Theme & Accessibility**: Light and dark mode with system preference detection, keyboard focus trapping, and WCAG 2.2 AA colour contrast
- **Privacy & Security First**: 100% client-side execution enforced by a strict Content Security Policy (`connect-src 'none'`)

## 📖 Usage

1. Paste your Base64-encoded (or URL-encoded) `SAMLResponse` into the text area
2. Click **Decode**
3. Expand **Raw XML** or **View raw certificate (PEM)** as needed, or click **Help** on any section for field definitions

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
