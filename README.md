# videojs-landscape-fullscreen

Fullscreen control:

- Rotate to landscape to enter Fullscreen
- Always enter fullscreen in landscape mode even if device is in portrait mode

## Installation

```sh
npm install --save videojs-landscape-fullscreen
```

## Plugin Options

### Default options

```js
{
  fullscreen: {
    enterOnRotate: true,         // Enter fullscreen mode on rotating the device in landscape
    alwaysInLandscapeMode: true, // Always enter fullscreen in landscape mode even when device is in portrait mode (works on chromium, firefox, and ie >= 11)
    iOS: true //Whether to use fake fullscreen on iOS (needed for displaying player controls instead of system controls)
  }
};
```

## Usage

To include videojs-landscape-fullscreen on your website or web application, use any of the following methods.

### React

```js
import React, { Component } from 'react'
import videojs from 'video.js'
import 'videojs-youtube'
import 'video.js/dist/video-js.css'

class Player extends Component {
  componentDidMount() {
    // instantiate Video.js
    this.player = videojs(this.videoNode, this.props, function onPlayerReady() {
      console.log('onPlayerReady', this)
    })
  }

  // destroy player on unmount
  componentWillUnmount() {
    if (this.player) {
      this.player.dispose()
    }
  }

  // wrap the player in a div with a `data-vjs-player` attribute
  // so videojs won't create additional wrapper in the DOM
  // see https://github.com/videojs/video.js/pull/3856
  render() {
    return (
      <div>
        <div data-vjs-player>
          <video ref={node => (this.videoNode = node)} className="video-js" />
        </div>
      </div>
    )
  }
}

export default Player
```

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

## Pull Requests

Feel free to open pull requests as long as there are no major changes in api surface area.

## License

MIT.


[videojs]: http://videojs.com/

## Credits

Heavily influenced from https://github.com/mister-ben/videojs-mobile-ui
