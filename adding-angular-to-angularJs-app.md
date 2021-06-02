## Migrating angular Js to angular


### 1. Install Migration Packages

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

### 2. Preparing for a Webpack Build

Web pack is a bundler and it take each files and create module out of it
As we need to bundle our Js and Template files, we need to change our
template Url from full to relative path.

```.js
// full path example
templateUrl: '/admin/adminLogin.html'

// relative path example
templateUrl: './adminLogin.html'
```

we need make changes to all global variable used in the project because 
Web pack will wrap each code in own module and existing code depended on
that code could cause side effect after bundling. Hence we need to use
long hand version in the angular js application.

```.js

// short hand global variable reference example
app.config(func .....

// long hand version for the same 
angular.module('app').config(func .....

```

We also need to update `tsconfig` file
1. add module information `{'module':'commmonjs'}`.
2. add module resolution setting `{'moduleResolution':'node'}`.

Now we need to create a entry point in the project hence create new `index.ts`
file. Now copy all the files from the existing `bundleconfig` or html and then 
use the same path and change import all those file in the new created 
`index.ts` file. Also remove `.js` from the path.


_existing reference_
```.html
<script type='text/javascript' src='/vendor/jquery.min.js'></script>
<script type='text/javascript' src='/vendor/toaster.min.js'></script>
...
```

_updated reference_
```.ts
 import './vendor/jquery.min';
 import './vendor/toaster.min';
...
```



