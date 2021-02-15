---
layout: post
title:  "Make Your Own MC Launcher"
date:   2021-02-15 21:16:03 +0700
categories: jekyll update
---
So Today We're Making Our Own Minecraft Launcher,

Step 1: 

Install NodeJS From [Here](https://nodejs.org)

Step 2:

Open The Folder For Your Launcher In PowerShell (Or Command Prompt), Run npm init -y,
Then Run npm i minecraft-launcher-core,

And Then Paste The Following Into The index.js File After Creating It.

```javascript
const { Client, Authenticator } = require('minecraft-launcher-core');
const launcher = new Client();

let opts = {
    clientPackage: null,
    authorization: Authenticator.getAuth("email@emailprovider.com", "minecraft_password"),
    root: "./minecraft",
    version: {
        number: "1.8.9",
        type: "release"
    },
    memory: {
        max: "4G",
        min: "2G"
    }
}

launcher.launch(opts);

launcher.on('debug', (e) => console.log(e));
launcher.on('data', (e) => console.log(e));
```

Step 3:

Edit The index.js Where You Can Change email@emailprovider.com With Your Minecraft.net Email & Editing minecraft_password With The Password.

Remember This Is Mojang Account Only.

Now, You Can Go Back To The Command Line, Before This Make Sure To Select The Minecraft Version, In The Script Above It Is 1.8.9, Once Selected You Can Run,

node index.js, Which Should Install Minecraft In The Launcher Directory, And It Should Launch Minecraft.

## Thanks For Reading!

Thanks For Reading, I'll See You In The Next One!
