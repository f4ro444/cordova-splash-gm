# cordova-splash-gm

Automatic splash screen resizing for Cordova. Add `splash.png` to the root folder of your Cordova project and use cordova-splash-gm to automatically resize, crop, copy and configure the splash screen for all current Android and iOS devices.

### Manual usage
1. `npm install -g cordova-splash-gm`
2. Place `splash.png` to the root folder of your Cordova project
3. Run `cordova-splash-gm`.

### Automated usage
1. `npm install cordova-splash-gm --save-dev`

2. Create `my-splash-hook.js`
    ```javascript
    var splash = require('cordova-splash-gm');
    
    module.exports = function() {
      return splash.generate();
    };
    ```

3. Add hook to `config.xml`
    ```xml
    <hook src="my-splash-hook.js" type="after_platform_add" />
    ```

That's it. Now every time you `cordova add platform`, the splash screens will be auto generated.

### Requirements
- GraphicsMagick
- At least one platform was added to your project
- Cordova's config.xml file must exist in the root folder

### Credits
All credit goes to [Alex Disler](https://github.com/AlexDisler) for his [cordova-icon](https://github.com/AlexDisler/cordova-icon) module, from which this project is forked from. The main changes are node's [imagemagick](https://www.npmjs.org/package/imagemagick) module is deprecated in favor of [gm](https://www.npmjs.org/package/gm) and the plugin can be used as a module in hooks.

### License

MIT
