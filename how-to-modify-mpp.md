# How to modify script.js

While there's lots of things you can do by just injecting JS, some things cannot be done because much of the code is protected in scope, so you have to modify the [script](http://www.multiplayerpiano.com/script.js) directly.

The old way of doing it was to put the script.js in Tampermonkey as a userscript, and block `http://www.multiplayerpiano.com/script.js` with AdBlock, but there is a better way using an extension specifically designed for this purpose, [Resource Override](https://chrome.google.com/webstore/detail/resource-override/pkoacgokdfckfpndoffpifphamojphii?hl=en).

1. Install [Resource Override](https://chrome.google.com/webstore/detail/resource-override/pkoacgokdfckfpndoffpifphamojphii?hl=en) extension for Chrome
2. Create a **Tab Rule** for `http://www.multiplayerpiano.com/*`
3. Create a **URL → File** rule for `*/script.js`
> Your rules should look like this: ![](https://i.imgur.com/m4ZZ4Mv.png)
4. Go to http://www.multiplayerpiano.com/script.js and copy all the code
5. Go back to Resource Override, click **Edit File** and paste the code in.

That's it! Now you can modify your copy and it should override the original script.

> You can use this method to modify other files, such as Client.js
