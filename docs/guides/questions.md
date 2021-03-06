# Questions the generator will ask
The generator will ask the following questions in that order:

## Name?
![image](https://cloud.githubusercontent.com/assets/1370779/15828173/91abb874-2c0e-11e6-81ee-c2608a751b14.png)

The name of the project will be written to the `config.xml` and thus show up below your app icon when you run the app on a device:
```html
<name>Adventure Island</name>
```
From this name the generator also derives a compatible **angular module name** for the root module of your app:

`app.js`:
```js
angular.module('adventureIsland', [
  // load your modules here
  'main', // starting with the main module
]);

```

This module is then bootstrapped in the `index.html`:
```html
<body ng-app="adventureIsland">
```

## App identifier?
![image](https://cloud.githubusercontent.com/assets/1370779/15828919/9ef7fe2c-2c11-11e6-9396-848a1a90c78f.png)

A reverse-domain identifier to identify your app. If you don't know what that is, a good explanation is found in the [psdpdfkit guides](https://pspdfkit.com/guides/ios/current/faq/what-is-a-bundle-id/). For a start you can just **make one up** and change it later.

`config.xml`:
```html
<widget id="com.company.project" ...>
```

## Ionic CSS or Sass?
![image](https://cloud.githubusercontent.com/assets/1370779/15851768/828afdce-2c9e-11e6-9fd4-032049de2290.png)

You'll be writing your own styles using Sass in any case. Your choice here is between including the Ionic styles as CSS or Sass.

No matter what choice you make, you can change this later, after project generation with the help of our [Ionic style source](./ionic_style_source.md) guide.

Choosing Sass allows you to change the basic layout of Ionic. Bar heights, colors and more. However the whole Ionic Sass needs to compile with every change you make to your own Sass, which is a little slower than if you just include the compiled CSS version of the Ionic styles. So if Ionic generally suffices for your project as is, go with the CSS version.


## Additional bower packages?
![image](https://cloud.githubusercontent.com/assets/1370779/15853161/3d21fbec-2ca4-11e6-9d81-dcec85b4aa2e.png)

The angular, ionic, angular-ui-router and ngCordova bower dependencies will be installed and included by default. Additional packages you select here also get installed and injected into your `index.html`. Refer to their documentations for instructions on how to use them, some are covered in our [Bower component usage](./bower_component_usage.md) guide.

Install new ones using the [Bower CLI](http://bower.io/docs/api/):
```sh
bower install angular-translate --save
```

## Cordova platforms?
![image](https://cloud.githubusercontent.com/assets/1370779/15854124/7704465e-2ca8-11e6-80e3-92a99243dffb.png)

Choose the platforms you want to build for. This will only work if you have the platforms' requirements correctly set up. For more information visit [Installation and Prerequisites](./installation_prerequisites.md).

You can add and remove platforms at any time using the Cordova CLI wrapper:
```sh
gulp --cordova "platform add android --save"
```
More detailed instructions are found in the [Development Introduction](./development_intro.md). So if you're not sure, leave these empty for now. A full list of platforms supported by Cordova is found in the [Cordova Documentation](https://cordova.apache.org/docs/en/latest/guide/support/).

## Cordova plugins?
![image](https://cloud.githubusercontent.com/assets/1370779/15854446/292c5122-2caa-11e6-95df-db9227f1d8ea.png)

Select the ones you want to install now. Unlike the Cordova platforms, these will not fail without the proper Cordova platform setup.

Just as with the platforms you can add plugins later at any time using the [Cordova CLI wrapper](./development_intro.md#using-the-cordova-cli):
```sh
gulp --cordova "plugin add org.apache.cordova.camera --save"
```
Find all available plugins on the [Cordova plugins page](https://cordova.apache.org/plugins/).

## Starter template?
![image](https://cloud.githubusercontent.com/assets/1370779/15855054/a47c9050-2cad-11e6-88e3-04d96add5e0a.png)

This choice decides whether your app will be generated with an [Ionic side menu](http://ionicframework.com/docs/api/directive/ionSideMenus/) or [Ionic tab navigation](http://ionicframework.com/docs/api/directive/ionTabs/). Alternatively you may choose to generate a blank module, if you wish to build everything from the ground up.

## Ecosystems?
![image](https://cloud.githubusercontent.com/assets/1370779/15855148/33988dca-2cae-11e6-8e19-f3b57c6ea797.png)

Generator-M-Ionic provides integration into different ecosystems. For more information refer to the [Ecosystems section of our Guides](../../README.md#ecosystems). If you don't know what these are, just leave them empty for now.
