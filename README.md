# Youtube Player

[![stable](http://hughsk.github.io/stability-badges/dist/stable.svg)](http://github.com/hughsk/stability-badges)

A bare bones wrapper around the Youtube Iframe API.

## Usage

```
const Youtube = require('youtube-player');

const player = new Youtube();
player.cue('dQw4w9WgXcQ', 6); // Start playback at 6 seconds
```

## Instance Methods

### new Youtube(el[, options])

Create a new player instance.

- `el` - an element that will be REPLACED by the player iframe.
- `options` - (OPTIONAL) - configuration parameters:

* controls: show or hide the default player controls
* allowFullscreen: enable/disable fullscreen
* hasAutoplay: automatically plays video - only works on desktop. Defaults to false
* hasCueAutoplay: control if `player.cue` automatically plays the video - autoplay only works on dekstop. Defaults to the `hasAutoplay` value.

The player size defaults to 100% so you should use a container for any positioning/resizing.

### cue(videoId[, startTime])

Change the displayed video.

- `videoId` - the youtube video hash (in the URL after `watch?v=`).
- `startTime` - (OPTIONAL) - time to start the video playback, in seconds.

### play()

Resume playback.

### pause()

Pause playback.

### seek(time)

Jump to a specific time.

- `time` - the time to jump to, in seconds.

### mute()

Mute the sound.

### unmute()

Unmutes the sound.

### volume(value)

Sets the sound volume.

- `value` - the volume, in 0-1 range.

### fullscreen()

Toggle the player to fullscreen, if supported. Note that this is using the javascript requestFullScreen API since Youtube doesn't support this, unless you use built-in controls.

### getDuration()

Return the current video duration.

### getVolume()

Return the current sound volume.

### getCurrentTime()

Return the current video time.

### isPopulated()

Return whether or not the player is ready (creating the player using YT API is asynchronous).

### isPlaying()

Return whether or not a video is currently playing.

### isMuted()

Return whether or not the sound is muted.

### hasPlayed()

Return whether or not a video has already started since the player was created.

### destroy()

Stop and destroy the player.

## Instance Events

### populated

### playing

### paused

### ended

### buffering

### unstarted

### cued

### timeupdate

## License

MIT.
