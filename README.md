# adf-widget-news

News widget for the [angular-dashboard-framework](https://github.com/sdorra/angular-dashboard-framework).

## Build

The widget is build with the help of [node](https://nodejs.org/), [npm](https://www.npmjs.com/), [bower](http://bower.io/) and [gulp](http://gulpjs.com/). For a install instruction for node and npm, please have a look [here](https://docs.npmjs.com/getting-started/installing-node).
Locally the widget can be built and tested with **node version 9**.

#### Installing bower and gulp

```bash
npm install -g bower
npm install -g gulp
```

#### Installing dependencies

```bash
npm install
bower install
```

#### Build the adf-widget-news

```bash
gulp
```

The compiled and optimized files can be found in the dist directory.

#### Other build goals

Each goal can be used as parameter for the gulp command.

* *clean*: removes the dist folder
* *lint*: checks css and javascript files for common errors
* *serve*: starts an webserver to test the widget

## Test in Cockpit
* Build adf-news-widget.
  ```bash
  gulp
  ```
* Replace contents of folder `app/client/bower_components/adf-widget-news/dist` in cockpit with the contents of the `dist folder.

## Usage

Install the widget with bower:

```bash
bower install adf-widget-news --save
```

Include the script in your index.html and be sure it is loaded after [angular](https://angularjs.org/) and after the [angular-dashboard-framework](https://github.com/sdorra/angular-dashboard-framework).
```html
<script type="text/javascript" src="bower_components/adf-widget-news/dist/adf-widget-news.min.js"></script>
```

Define a dependency for the module:

```javascript
angular.module('sample', ['adf', 'adf.widget.news']);
```

Define the URL of the service which converts a rss feed into json:

 ```javascript
 .constant('newsServiceUrl', '<URL>')
 ```
 The expected response structure is based on the node module [rss-parser](https://www.npmjs.com/package/rss-parser)
