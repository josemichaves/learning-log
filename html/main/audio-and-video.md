# Audio and Video

We can display audio and video in a html file, with the correspondent tags.

## Audio

```markup
<audio controls muted autoplay>
    <source src='hello.ogg' type='audio/ogg' />
    <source src='goodbye.mp3' type='audio/mpeg' />
    Your browser doesn't support the audio element
</audio>
```

This is how we can embed audio in our pages, we call the `audio` tag, and inside it we call the `source` tag to specify what we want to be played, we also need to specify which type of audio file is it.

We can pass various parameters to the `audio` tag, the `controls` will show the audio controls \(play, pause, volume, etc.\) the `muted` will make it so that when we enter our website the sound is muted, and finally the `autoplay` will make when we entry the page will start to play the audio source. All of these parameters are optional.

The text is if the browser doesn't support the audio tag, we'll show this text instead.

## Video

```markup
<video width="320" height="240" controls>
  <source src="movie.mp4" type="video/mp4">
  <source src="movie.ogg" type="video/ogg">
Your browser does not support the video tag.
</video>
```

Video is quite similar to audio, we call the `video` tag and inside it we specify our sources, we need to specify also the type of the source.

We can pass the same parameters as audio \(`controls, muted, autoplay`\) they work in the same way. But we have a  specific parameters to audio, these are the `width` and the `height`, that allow us to specify the size of the video element inside the HTML, we can do it also with CSS.

