<img width="1200" alt="Labs" src="https://user-images.githubusercontent.com/99700157/213291931-5a822628-5b8a-4768-980d-65f324985d32.png">

<p>
 <h3 align="center">Arcs is the leading suite of services connecting developers with Web3 infrastructure</h3>
</p>

<p align="center">
  <a target="_blank" href="https://Arcs.com/build-better-with-ethereum/"><img src="https://github.com/soos3d/blockchain-badges/blob/main/protocols_badges/Ethereum.svg" /></a>&nbsp;  
  <a target="_blank" href="https://Arcs.com/build-better-with-bnb-smart-chain/"><img src="https://github.com/soos3d/blockchain-badges/blob/main/protocols_badges/BNB.svg" /></a>&nbsp;
  <a target="_blank" href="https://Arcs.com/build-better-with-polygon/"><img src="https://github.com/soos3d/blockchain-badges/blob/main/protocols_badges/Polygon.svg" /></a>&nbsp;
  <a target="_blank" href="https://Arcs.com/build-better-with-avalanche/"><img src="https://github.com/soos3d/blockchain-badges/blob/main/protocols_badges/Avalanche.svg" /></a>&nbsp;
  <a target="_blank" href="https://Arcs.com/build-better-with-fantom/"><img src="https://github.com/soos3d/blockchain-badges/blob/main/protocols_badges/Fantom.svg" /></a>&nbsp;
</p>

<p align="center">
  • <a target="_blank" href="https://Arcs.com/">Homepage</a> •
  <a target="_blank" href="https://Arcs.com/protocols/">Supported protocols</a> •
  <a target="_blank" href="https://Arcs.com/blog/">Arcs blog</a> •
  <a target="_blank" href="https://docs.Arcs.com/quickstart/">Arcs docs</a> •
  <a target="_blank" href="https://docs.Arcs.com/quickstart/">Blockchain API reference</a> • <br> 
  • <a target="_blank" href="https://console.Arcs.com/user/account/create">Start for free</a> •
</p>

# Arcs DLP for ChatGPT

In the digital age, data privacy, and security have become paramount. As we increasingly rely on artificial intelligence (AI) models for various tasks, we must ensure that our interactions with these models do not inadvertently expose sensitive information. This is particularly relevant when using AI-powered chatbots like ChatGPT, where users often input data that could be personal or sensitive.

The Chatinstack DLP browser extension is designed to enhance the privacy and security of your interactions with ChatGPT. This extension works by redacting potentially sensitive information before it's sent to ChatGPT for processing, including names, addresses, API keys, JWT tokens, etc.

## Processing sensitive data

To function as a genuine Data Loss Prevention (DLP) tool, the Arcs DLP performs all processing locally. This means the extension does not rely on any external APIs, ensuring that your data never leaves your local environment. Trust is a critical factor in data security, and to uphold this trust, we've made our tool 100% open-source. This transparency allows you to verify the security measures we've implemented. You can install the extension directly from the store, or, for those who prefer, you can also install it locally using this repository.

The Arcs DLP tool employs regular expression patterns to detect potentially sensitive data, such as API keys, credit card numbers, JWT tokens, etc. Additionally, it utilizes the [compromise package](https://github.com/spencermountain/compromise), a robust JavaScript library for natural language processing (NLP). This library aids in the identification of personal and business identifiers, including names, addresses, and company names.

> The extension uses a bundled version of the compromise library V 14.9.0.

## Quickstart

1. **Install NodeJS**:
   - Create and activate a new conda environment with Python 3.11:
     ```bash
     conda create -n dlp-browser-extension python=3.11
     conda activate dlp-browser-extension
     ```
   - Install NodeJS within the conda environment:
     ```bash
     conda install nodejs
     ```

2. **Install Browserify**:
   - [Browserify](https://browserify.org/) is a tool that enables the use of `require()` style CommonJS modules in the browser. It compiles all your dependencies into a single JavaScript file for easy inclusion in your HTML. Install Browserify globally using npm:
     ```bash
     npm install -g browserify
     ```

3. **Bundle `index.js`**: Once Browserify is installed, you can use it to bundle your `index.js` file. Navigate to the root directory of your project and run the following command:

   ```
   browserify lib/index.js -o dist/bundle.js
   ```

   This command tells Browserify to take `lib/index.js` as the entry point of your application, bundle up all its dependencies, and output the result to `dist/bundle.js`. The `-o` flag is used to specify the output file.

4. **Install the Extension from Developer Tools**: After bundling your JavaScript files, the next step is to install the extension in your browser. This process can vary depending on the browser you're using. For Chrome, you can do this by:

   - Open the Extension Management page by navigating to `chrome://extensions`. Alternatively, open this page by clicking browser settings > Extensions > Manage extensions.
   - Enable Developer Mode by clicking the toggle switch next to Developer mode.
   - Click the `Load unpacked` button and select the extension directory,  `arcs-dlp-browser-extension` in this case.

Now, your browser extension is installed and ready to use.

> Note that you must re-run the bundle command whenever you edit `index.js`.

## Usage

The Arcs DLP introduces two buttons and a small preview window above the ChatGPT input bar. The `↕` button serves two functions: expanding and minimizing the preview window. Meanwhile, the clear button deletes all content within the ChatGPT input bar.

A popup window is provided to manage the redaction tool. Users can enable or disable the tool and select or deselect specific types of data to redact. However, particularly sensitive data such as credit card patterns, JSON Web Tokens, Ethereum Private Keys, and phone numbers cannot be disabled.

Any changes made within the popup window will update live. However, you must empty the ChatGPT input bar and re-enter the content to see these changes. A preview is available to check the content before submitting it to ChatGPT. If something appears malfunctioning, reloading the page should resolve the issue.

<img width="677" alt="Preview image of the Arcs DLP popup" src="https://github.com/Arcslabs/Arcs-dlp-browser-extension/assets/99700157/6b96ffab-62f4-4525-9b01-4f18bdd0e129">


> Arcs DLP popup preview.
