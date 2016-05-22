# Load-Settings

This package loads a settings.js file on root directory and made it available everywhere by require("load-settings").

## Instalation

```bash
npm install load-settings --save
```


# How this works

First, inside your root directory create a file **settings.js** and inside of this file put your variables on a JSON document.

```javascript
// settings.js
module.exports = {
  AUTH: {
    GITHUB: {
      CLIENT_ID: process.env.GITHUB_KEY,
      CLIENT_SECRET: process.env.GITHUB_SECRET,
      CALLBACK_URL: process.env.APP_URL + 'auth/github/callback',
      SCOPE: ["user"]
    }
  },
  PROJECT_DIR: __dirname
};
```
Then anytime you want your settings variables just use
```javascript
  var settings = require("load-settings");
  settings.PROJECT_DIR; 
```