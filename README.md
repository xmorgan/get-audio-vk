## get-audio-vk

Parse **audios** from user or public in VK

#### Scripts

`Development` Mode - yarn dev

`Production` Mode - yarn build

#### Usage

1. Create **.env**
2. Fill **variables** like .env.template

3.

```javascript
const ParseAudios = require("get-audio-vk").default;
const startBrowser = require("get-audio-vk/dist/browser").default;
const makeAuthBrowser = require("get-audio-vk/dist/make-auth-browser").default;

let browser = null;
let parse = null;

(async () => {
  browser = await startBrowser(false);
  await makeAuthBrowser(browser);
  parse = new ParseAudios(browser);
})();

const targetID = 13323123;
const cookie = "remixlang=0; remixstid=1326033251_8da2AvbCV8rZJN...";
const maxTracks = 5;

parse.run(targetID, cookie, maxTracks);
```
