# PareJS

PareJS is a JavaScript library which provides advanced cropping image editing tools in
your browser, such as **rotation**, **cropping**, **color tone** and **managing resolutions**. It is based on the awesome
[DarkroomJS](https://mattketmo.github.io/darkroomjs/).

## Why name it Pare?
**pare — /pɛə/** _verb (transitive)_
* to peel or cut (the outer layer) from (something)
* to cut the edges from (the nails); trim
* to decrease bit by bit

The intention of this fork is to do more than darkroom already has. To focus on staging images in containers of aspect ratios and resolutions needed for a website, app or other publishing while forcing the photographer to maintain the needed quality.

## Demo

Try the online demo at [http://mattketmo.github.io/darkroomjs](http://mattketmo.github.io/darkroomjs/)

The library is currently *work in progress*.
I know there is some bug especially when resizing the crop zone.
Feel free to fork the project or report issues on GitHub.
All ideas are also welcome.

## Building

- Install [Node](http://nodejs.org/)
- Install [Grunt](http://gruntjs.com/)
- The webfont is auto generated from SVG icons.
  This uses the [grunt-webfont](https://github.com/sapegin/grunt-webfont) task which
  requires `fontforge` and `ttfautohint`. See [the readme](https://github.com/sapegin/grunt-webfont#installation)
  for more details.
- Run `npm install`
- Run `grunt build`

Every assets will be generated into the `build/` directory.

## Usage

Simply instanciate a new Darkroom object with a reference to the image element:

```html
<img src="some-image.jpg" id="target">
<script>
  new Darkroom('#target');
</script>
```

You can also pass some options:

```javascript
new Darkroom('#target', {
  // Canvas initialization size
  minWidth: 100,
  minHeight: 100,
  maxWidth: 500,
  maxHeight: 500,

  // Plugins options
  plugins: {
    crop: {
      minHeight: 50,
      minWidth: 50,
      ratio: 1
    },
    save: false // disable plugin
  },
});
```

## Why?

It's easy to get a javascript script to crop an image in a web page.
But if your want more features like rotation or brightness adjustment, then you
will have to do it yourself. No more jQuery plugins here.
It only uses the power of HTML5 canvas to make what ever you want with your image.

## The concept

The library is designed to be easily extendable. The core script only transforms
the target image to a canvas with a FabricJS instance, and creates an empty toolbar.
All the features are then implemented in separate plugins.

Each plugin is responsible for creating its own functionality.
Buttons can easily be added to the toolbar and binded with those features.

## License

DarkroomJS is released under the MIT License. See the [bundled LICENSE file](LICENSE)
for details.

