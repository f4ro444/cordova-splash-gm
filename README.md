# cordova-splash

Automatic splashscreen resizing for Cordova. Create a splashscreen in the root folder of your Cordova project and use cordova-splash to automatically resize and copy it for all the platforms your project supports (currenty works with iOS and Android).

### Installation

     $ sudo npm install cordova-splash -g

### Usage
     
Create a ```splash.png``` file in the root folder of your cordova project and run:

     $ cordova-splash

### Creating a cordova-cli hook

Since the execution of cordova-splash is pretty fast, you can add it as a cordova-cli hook to execute before every build.
To create a new hook, go to your cordova project and run:

    $ mkdir hooks/after_prepare
    $ vi hooks/after_prepare/cordova-splash.sh

Paste the following into the hook script:

    #!/bin/bash
    cordova-splash

Then give the script +x permission:

    $ chmod +x hooks/after_prepare/cordova-splash.sh

That's it. Now every time you ```cordova build```, the splashscreens will be auto generated.

### Requirements

- ImageMagick

Install on a Mac:

     $ brew install imagemagick

- At least one platform was added to your project ([cordova platforms docs](http://cordova.apache.org/docs/en/3.4.0/guide_platforms_index.md.html#Platform%20Guides))
- Cordova's config.xml file must exist in the root folder ([cordova config.xml docs](http://cordova.apache.org/docs/en/3.4.0/config_ref_index.md.html#The%20config.xml%20File))

### Credits
All credit goes to [Alex Disler](https://github.com/AlexDisler) for his [cordova-icon](https://github.com/AlexDisler/cordova-icon) module, this is merely a fork with different values.


### License

MIT
