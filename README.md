# videojs-landscape-fullscreen



## Installation

```sh
npm install --save videojs-landscape-fullscreen
```

## Usage

To include videojs-landscape-fullscreen on your website or web application, use any of the following methods.

### `<script>` Tag

This is the simplest case. Get the script in whatever way you prefer and include the plugin _after_ you include [video.js][videojs], so that the `videojs` global is available.

```html
<script src="//path/to/video.min.js"></script>
<script src="//path/to/videojs-landscape-fullscreen.min.js"></script>
<script>
  var player = videojs('my-video');

  player.landscapeFullscreen();
</script>
```

### Browserify/CommonJS

When using with Browserify, install videojs-landscape-fullscreen via npm and `require` the plugin as you would any other module.

```js
var videojs = require('video.js');

// The actual plugin function is exported by this module, but it is also
// attached to the `Player.prototype`; so, there is no need to assign it
// to a variable.
require('videojs-landscape-fullscreen');

var player = videojs('my-video');

player.landscapeFullscreen();
```

### RequireJS/AMD

When using with RequireJS (or another AMD library), get the script in whatever way you prefer and `require` the plugin as you normally would:

```js
require(['video.js', 'videojs-landscape-fullscreen'], function(videojs) {
  var player = videojs('my-video');

  player.landscapeFullscreen();
});
```

## License

MIT. Copyright (c) Prateek Rastogi


[videojs]: http://videojs.com/
