Play Video on Scroll jQuery Plugin
-----------------------------

Download the js file here:
[https://github.com/jrue/play-video-on-scroll/blob/main/example/js/jquery-video-scroll.js](https://github.com/jrue/play-video-on-scroll/blob/main/example/js/jquery-video-scroll.js)

Play a video animation as you scroll down. [See example here (scroll down the page)](https://jrue.github.io/play-video-on-scroll/example/)

This requires you to first use a program like ffmpeg to separate each frame of the video into dozens of images. This plugin will preload them. It's not recommended to have more than about 200 images, therefore the video should be only a couple of seconds long.

ffmpeg command to export 30fps into jpg files with three digit padding:

```bash
ffmpeg -i video.mp4 -r 30 $filename%03d.jpg
```

HTML:

```html
<div style="height:200vh;">
  <canvas style="position:sticky;top:0;"></canvas>
</div>
```

JavaScript (with all options):

```javascript
$( 'canvas' ).videoScroll({
  width: 960,
  height: 540,
  imageFolder: 'images',
  imageType: 'jpg',
  imageCount: 60,
  digits: 3
});
```

#### Options

**imageFolder** - the folder with all of the images.
**imageType** - file extension of the images.
**imageCount** - IMPORTANT! How many images do you have?
**digits** - For zero padding. Three digits is 001.jpg, 002.jpg, etc.

Canvas is responsive, but we need a width and height to calculate the ratio.



