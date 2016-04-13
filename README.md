# angular-smooth-scrollbar

[![npm](https://img.shields.io/npm/v/angular-smooth-scrollbar.svg?style=flat-square)](https://www.npmjs.com/package/angular-smooth-scrollbar)
[![npm](https://img.shields.io/npm/l/angular-smooth-scrollbar.svg?style=flat-square)](https://www.npmjs.com/package/angular-smooth-scrollbar)
[![devDependency Status](https://img.shields.io/david/dev/idiotWu/angular-smooth-scrollbar.svg?style=flat-square)](https://david-dm.org/idiotWu/angular-smooth-scrollbar#info=devDependencies)
[![npm](https://img.shields.io/npm/dt/angular-smooth-scrollbar.svg?style=flat-square)](https://www.npmjs.com/package/angular-smooth-scrollbar)
[![Travis](https://img.shields.io/travis/idiotWu/angular-smooth-scrollbar.svg)](https://travis-ci.org/idiotWu/angular-smooth-scrollbar)

[smooth-scrollbar](https://github.com/idiotWu/smooth-scrollbar) for angular projects.

## Requirements

Angular 1.4+

## Install

Via npm:

```
npm install angular-smooth-scrollbar --save
```

Or via bower:

```
bower install angular-smooth-scrollbar --save
```

## Demo

[http://idiotwu.github.io/angular-smooth-scrollbar/](http://idiotwu.github.io/angular-smooth-scrollbar/)


## Usage

1. Include all dependencies in your page file:

    ```html
    <link rel="stylesheet" href="smooth-scrollbar/dist/smooth-scrollbar.css">

    <script src="angular.js"></script>
    <script src="smooth-scrollbar/dist/smooth-scrollbar.js"></script>
    <script src="angular-smooth-scrollbar/dist/angular-smooth-scrollbar.js"></script>
    ```

2. Add `SmoothScrollbar` as dependency to your angular app:

    ```javascript
    angular.module('myApp', ['SmoothScrollbar']);
    ```

3. Use it wherever you want:

    - As element:

        ```html
        <scrollbar name="scrollbarName">
            ...
        </scrollbar>
        ```

    - As attribute:

        ```html
        <section scrollbar="scrollbarName">
            ...
        </section>
        ```

### Available Options

| parameter | type | default | description |
| :--------: | :--: | :-----: | :----------: |
| speed | Number | 1 | Scrolling speed scale.|
| friction | Number | 10 | Scrolling friction, a percentage value within (1, 100). |
| thumbMinWidth | Number | 20 | Minimal size for horizontal thumb. |
| thumbMinHeight | Number | 20 | Minimal size for vertical thumb. |
| continuousScrolling | Boolean | false | Whether allow upper scrollable content to continue scrolling when current scrollbar reaches edge. |
| ignoreEvents | Array | [] | A list of events names that are ignored, regex rules are supported. Details [here](https://github.com/idiotWu/smooth-scrollbar/wiki/Options-Field). |

**Confusing with the option field? Try edit tool [here](http://idiotwu.github.io/smooth-scrollbar/)!**

## ScrollbarServiceProvider

You can configure default scrollbar behavior here:

```javascript
angular.module('myApp', ['SmoothScrollbar'])
.config((ScrollbarServiceProvider) => {
    // set default scrollbar behavior
});
```

### ScrollbarServiceProvider.setDefaultOptions( options )

Set default scrollbar options for your angular app.


## ScrollbarService

By given scrollbar a name via attribute, you can access your scrollbar instances through `ScrollbarService`.

## ScrollbarService.generateName()

Return a timestamp string, this will be useful while trying naming scrollbars uniquely.

### ScrollbarService.getInstance( name )

Get scrollbar instance by giving the name, and return a promise with instance.

### ScrollbarService.destroyInstance( name )

Remove all event listeners on the named instance, but will not remove scrollbar from DOM.

## APIs

[Documents](https://github.com/idiotWu/smooth-scrollbar#apis)

## License

MIT.
