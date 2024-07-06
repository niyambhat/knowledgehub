---
sidebar_position: 3
---

# Media Player

There are several ways to implement videos in React. 
One of the most popular way is a third-party npm package React player. 
This is one of the most trusted and maintained package. Both React Player and the video tag in HTML are used to display video content in web applications, but they have some differences in terms of their features and usage.

## Using video syntax 

The video tag is a standard HTML element that can be used to embed a video in a web page. It has basic functionality and can display a video in various formats such as MP4, WebM, and Ogg. The video tag provides basic controls for the video, such as play, pause, volume control, and full-screen mode. It also supports some events such as onplay, onpause, onended, etc. which can be used to perform certain actions in response to user actions or video events. 

```JSX
import React from 'react';

function VideoPlayer() {
  return (
    <div>
      <video src="https://example.com/video.mp4" controls />
    </div>
  );
}

export default VideoPlayer;

```

## Using React Player 

On the other hand, React Player is a third-party library built on top of the  tag that provides additional features and flexibility for playing videos in React applications. React Player supports a wider range of video formats and provides more advanced features such as custom controls, playback speed control, subtitles, and the ability to play audio-only content. React Player also provides a React component that can be easily integrated into a React application, and allows for more fine-grained control of the video playback through its props and event handlers.

```JSX
import React, { useState } from 'react';
import ReactPlayer from 'react-player';

const MediaPlayer = () => {
  const [playing, setPlaying] = useState(false);
  const [volume, setVolume] = useState(0.8);
  const [speed, setSpeed] = useState(1);
  const [played, setPlayed] = useState(0);
  const [loaded, setLoaded] = useState(0);
  const [duration, setDuration] = useState(0);
  const [elapsed, setElapsed] = useState(0);
  const [remaining, setRemaining] = useState(0);

  const handlePlay = () => setPlaying(!playing);
  const handlePause = () => setPlaying(playing);

  const handleVolumeChange = (value) => setVolume(value);
  const handleSpeedChange = (value) => setSpeed(value);

  const handleProgress = (state) => {
    setPlayed(state.played);
    setLoaded(state.loaded);
    setElapsed(state.playedSeconds);
    setRemaining(state.playableSeconds - state.playedSeconds);
  };

  const handleDuration = (duration) => setDuration(duration);

  return (
    <div className="media-container">
      <ReactPlayer
        url="https://www.facebook.com/facebook/videos/10153231379946729/"
        playing={playing}
        volume={volume}
        playbackRate={speed}
        onProgress={handleProgress}
        onDuration={handleDuration}
      />
      <div className="controls">
        <h4>Controls</h4>
        <button onClick={handlePlay}>{playing ? 'Pause' : 'Play'}</button>
        <button onClick={handlePause}>{playing ? 'Pause' : 'Play'}</button>
      </div>
      <input
        type="range"
        min={0}
        max={duration}
        step={0.1}
        value={elapsed}
        onChange={(e) => setElapsed(parseFloat(e.target.value))}
      />
      <input
        type="range"
        min={0.5}
        max={2}
        step={0.1}
        value={speed}
        onChange={(e) => handleSpeedChange(parseFloat(e.target.value))}
      />

      <div className="progress">
        <div className="elapsed">{elapsed.toFixed(0)} seconds elapsed</div>
        <div className="duration">{duration.toFixed(0)} seconds total</div>
        <div className="remaining">{remaining.toFixed(0)} seconds remaining</div>
      </div>
    </div>
  );
};


export default MediaPlayer

```