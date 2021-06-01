## Migrating angular Js to angular


1. Install Migration Packages

To upgrade angularJs application to angular we need to first install
angular related dependencies in the existing package.json files. That are:

* @angular/common: '10.0'
* @angular/compiler: '10.0'
* @angular/core: '10.0'
* @angular/forms: '10.0'
* @angular/http: '10.0'
* @angular/platform-browser: '10.0'
* @angular/platform-browser-dynamic: '10.0'
* @angular/router: '10.0'
* @angular/upgrade: '10.0'

And the most important package which make our work easy is @angular/upgrade
package.

Also 3 more dependencies are

* @core-js:
* rxjs:
* zone.js:

Now we need to add some utilities from the angular in our dev dependecies

* @angular/complier-cli: 'latest-version'
* @ngtools/webpack: 'latest-version'
* @type/node: 'latest-version'
* angular2-template-loader: 'latest-version'
* awesome-typescript-loader: 'latest-version'
* html-loader: 'latest-version'
* html-webpack-plugin: 'latest-version'
* karma-mocha-reporter: 'latest-version'
* karma-webpack: 'latest-version'
* null-loader: 'latest-version'
* raw-loader: 'latest-version'
* rimraf: 'latest-version'
* webpack: 'latest-version'
* webpack-bundle-analyzer: 'latest-version'

Now install the packages using command

```
npm i

```



