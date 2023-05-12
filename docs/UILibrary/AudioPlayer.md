---
sidebar_position: 4
---

# Audio Player 


An example of Spotify Like Audio Player. This can be expanded to include playlists from a data source such as an api or cloud storage. 


```JSX
import React, { useState } from 'react';
import { FaPlay, FaPause, FaVolumeUp, FaVolumeDown, FaVolumeMute, FaChevronRight, FaChevronLeft } from 'react-icons/fa';
import './AudioPlayer.css';

function AudioPlayer() {
    const [isPlaying, setIsPlaying] = useState(false);
    const [volume, setVolume] = useState(0.5);
    const [currentTime, setCurrentTime] = useState(0);

    const song = new Audio("http://commondatastorage.googleapis.com/codeskulptor-demos/riceracer_assets/music/lose.ogg");
    song.volume = volume;
    song.currentTime = currentTime;

    const play = () => {
        if (song.pause) song.play();
    }
    const pause = () => {
        if (song.play) song.pause();
    }

    const handleVolumeChange = (event) => {
        setVolume(event.target.value);
        song.volume = event.target.value;
    };

    const handleTimeUpdate = () => {
        setCurrentTime(song.currentTime);
    };

    const handleSeek = (event) => {
        const seekTime = (event.nativeEvent.offsetX / event.target.offsetWidth) * song.duration;
        setCurrentTime(seekTime);
        song.currentTime = seekTime;
    };

    return (
        <div className="audio-player">
            <div className="audio-player__controls">
                <button className="audio-player__button" onClick={() => play()}>
                    <FaPlay />
                </button>
                <button className="audio-player__button" onClick={() => pause()}>
                    <FaPause />
                </button>
                <div className="audio-player__progress" onClick={handleSeek}>
                    <div className="audio-player__progress-bar" style={{ width: `${(currentTime / song.duration) * 100}%` }}></div>
                </div>
                <div className="audio-player__volume">
                    {volume === 0 ? <FaVolumeMute /> : volume < 0.5 ? <FaVolumeDown /> : <FaVolumeUp />}
                    <input className="audio-player__volume-slider" type="range" min="0" max="1" step="0.01" value={volume} onChange={handleVolumeChange} />
                </div>
            </div>
            <div className="audio-player__info">
                <div className="audio-player__title">Song Title</div>
                <div className="audio-player__artist">Artist Name</div>
            </div>
            <div className="audio-player__navigation">
                <button className="audio-player__button"><FaChevronLeft /></button>
                <button className="audio-player__button"><FaChevronRight /></button>
            </div>
        </div>
    );
}

export default AudioPlayer;

```