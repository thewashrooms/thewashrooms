---
layout: page
title: Brother/Numb
permalink: /music/brother/
---
<div class="music-page-content">

<html lang="en">
<head>
<meta charset="UTF-8">
<style>
.cassette-container {
  font-family: 'Courier New', monospace;
  max-width: 800px;
  margin: 0 auto;
  padding: 20px;
}

@keyframes spin {
  from { transform: rotate(0deg); }
  to { transform: rotate(360deg); }
}

@keyframes bounce {
  0% { height: 30%; }
  100% { height: 85%; }
}

.tracklist h2 {
  color: #ffffffff;
  font-size: 22px;
  margin-bottom: 20px;
  text-shadow: 2px 2px #000;
}

.track-item {
  padding: 12px 15px;
  margin: 8px 0;
  background-color: #2a2a2a;
  color: #b8b8b8;
  border: 2px solid #4a4a4a;
  cursor: pointer;
  font-size: 16px;
  box-shadow: 3px 3px 0 #000;
  transition: all 0.2s;
}

.track-item:hover {
  background-color: #3a3a3a;
  border-color: #6a6a6a;
}

.track-item.active {
  background-color: #a7001cff;
  color: #fff;
  border-color: #a7001cff;
}

.cassette-deck {
  background: linear-gradient(135deg, #2a2a2a 0%, #1a1a1a 100%);
  border: 4px solid #3a3a3a;
  border-radius: 8px;
  padding: 25px;
  box-shadow: 0 8px 16px rgba(0,0,0,0.6), inset 0 2px 4px rgba(255,255,255,0.05);
  display: none;
  margin-top: 30px;
}

.cassette-deck.active {
  display: block;
}

.now-playing {
  text-align: center;
  color: #a51d34ff;
  font-size: 18px;
  margin-bottom: 20px;
  font-weight: bold;
  text-shadow: 1px 1px #000;
}

.cassette-body {
  background: linear-gradient(180deg, #4a4a4a 0%, #2a2a2a 100%);
  border: 3px solid #1a1a1a;
  border-radius: 6px;
  padding: 20px;
  box-shadow: inset 0 2px 8px rgba(0,0,0,0.5);
}

.tape-window {
  background: linear-gradient(180deg, #1a1a1a 0%, #0a0a0a 100%);
  border: 2px solid #3a3a3a;
  border-radius: 4px;
  padding: 15px;
  display: flex;
  justify-content: space-around;
  align-items: center;
  margin-bottom: 15px;
  box-shadow: inset 0 2px 6px rgba(0,0,0,0.8);
}

.reel {
  width: 70px;
  height: 70px;
  border: 3px solid #5a5a5a;
  border-radius: 50%;
  background: radial-gradient(circle, #3a3a3a 0%, #1a1a1a 100%);
  position: relative;
  box-shadow: 0 2px 6px rgba(0,0,0,0.5), inset 0 1px 3px rgba(255,255,255,0.1);
  animation: spin 2s linear infinite;
  animation-play-state: paused;
}

.reel.spinning {
  animation-play-state: running;
}

.reel-center {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 24px;
  height: 24px;
  background: radial-gradient(circle, #2a2a2a 0%, #0a0a0a 100%);
  border-radius: 50%;
  border: 2px solid #1a1a1a;
  box-shadow: inset 0 1px 3px rgba(0,0,0,0.8);
}

.reel-hole {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 8px;
  height: 8px;
  background: #000;
  border-radius: 50%;
  box-shadow: 0 0 3px rgba(0,0,0,0.9);
}

.spoke {
  position: absolute;
  top: 50%;
  left: 50%;
  width: 1px;
  height: 30px;
  background: linear-gradient(180deg, #6a6a6a 0%, #3a3a3a 100%);
  transform-origin: top center;
  box-shadow: 0 0 1px rgba(255,255,255,0.3);
}

.tape-teeth {
  position: absolute;
  bottom: -3px;
  left: 50%;
  transform: translateX(-50%);
  width: 80%;
  height: 4px;
  background: repeating-linear-gradient(90deg, #4a4a4a 0px, #4a4a4a 2px, transparent 2px, transparent 4px);
}

.equalizer {
  display: flex;
  gap: 5px;
  height: 50px;
  align-items: flex-end;
  padding: 5px 12px;
  background: rgba(0,0,0,0.3);
  border-radius: 3px;
  border: 1px solid #2a2a2a;
}

.eq-bar {
  width: 6px;
  height: 30%;
  background: linear-gradient(180deg, #d10224ff 0%, #a7001cff 100%);
  border-radius: 1px;
  box-shadow: 0 0 3px #52000eff(139,107,183,0.5);
}

.eq-bar.active {
  animation: bounce 0.6s ease-in-out infinite alternate;
  box-shadow: 0 0 6px #690012ff;
}

.tape-label {
  background: linear-gradient(180deg, #e8d4b0 0%, #d4c0a0 100%);
  border: 2px solid #8b7355;
  padding: 10px;
  text-align: center;
  color: #2a2a2a;
  font-size: 13px;
  margin-top: 12px;
  border-radius: 3px;
  box-shadow: inset 0 1px 2px rgba(255,255,255,0.5);
  font-weight: bold;
}

.screws {
  display: flex;
  justify-content: space-between;
  padding: 0 10px;
  margin-bottom: 10px;
}

.screw {
  width: 8px;
  height: 8px;
  border-radius: 50%;
  background: radial-gradient(circle at 30% 30%, #5a5a5a, #2a2a2a);
  border: 1px solid #1a1a1a;
  position: relative;
}

.screw::after {
  content: '';
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%) rotate(45deg);
  width: 5px;
  height: 1px;
  background: #1a1a1a;
}

.controls {
  display: flex;
  gap: 12px;
  justify-content: center;
  margin: 20px 0;
}

.btn {
  padding: 12px 28px;
  font-size: 20px;
  border: 3px solid;
  color: #fff;
  cursor: pointer;
  font-weight: bold;
  box-shadow: 3px 3px 0 #000, inset 0 1px 2px rgba(255,255,255,0.2);
  font-family: monospace;
  border-radius: 4px;
  transition: all 0.1s;
}

.btn:active {
  transform: translate(2px, 2px);
  box-shadow: 1px 1px 0 #000, inset 0 1px 2px rgba(255,255,255,0.2);
}

.play-btn {
  background: linear-gradient(180deg, #00cbdaff 0%, rgba(19, 87, 114, 1) 100%);
  border-color: #000000ff;
}

.stop-btn {
  background: linear-gradient(180deg, #b80000ff 0%, #690000ff 100%);
  border-color: #000000ff;
}

.progress-container {
  margin: 15px 0;
  padding: 0 5px;
}

.progress-bar {
  width: 100%;
  height: 8px;
  background: #1a1a1a;
  border: 2px solid #2a2a2a;
  border-radius: 4px;
  cursor: pointer;
  position: relative;
  box-shadow: inset 0 2px 4px rgba(0,0,0,0.5);
}

.progress-fill {
  height: 100%;
  background: linear-gradient(90deg, #8b6bb7 0%, #6a4a8a 100%);
  border-radius: 2px;
  width: 0%;
  transition: width 0.1s;
  box-shadow: 0 0 4px rgba(139,107,183,0.6);
}

.time-display {
  display: flex;
  justify-content: space-between;
  color: #8b8b8b;
  font-size: 14px;
  margin-top: 5px;
}
</style>
</head>
<body>

<div class="cassette-container">
  <div class="tracklist">
    <h2>▶ TRACKLIST</h2>
    <div id="track-list"></div>
  </div>

  <div class="cassette-deck" id="deck">
    <div class="now-playing" id="now-playing"></div>
    
    <div class="cassette-body">
      <div class="screws">
        <div class="screw"></div>
        <div class="screw"></div>
        <div class="screw"></div>
        <div class="screw"></div>
      </div>

      <div class="tape-window">
        <div class="reel" id="left-reel">
          <div class="reel-center">
            <div class="reel-hole"></div>
          </div>
          <div class="spoke" style="transform: translate(-50%, 0) rotate(0deg)"></div>
          <div class="spoke" style="transform: translate(-50%, 0) rotate(30deg)"></div>
          <div class="spoke" style="transform: translate(-50%, 0) rotate(60deg)"></div>
          <div class="spoke" style="transform: translate(-50%, 0) rotate(90deg)"></div>
          <div class="spoke" style="transform: translate(-50%, 0) rotate(120deg)"></div>
          <div class="spoke" style="transform: translate(-50%, 0) rotate(150deg)"></div>
          <div class="tape-teeth"></div>
        </div>

        <div class="equalizer">
          <div class="eq-bar" style="animation-delay: 0s"></div>
          <div class="eq-bar" style="animation-delay: 0.1s"></div>
          <div class="eq-bar" style="animation-delay: 0.2s"></div>
          <div class="eq-bar" style="animation-delay: 0.15s"></div>
          <div class="eq-bar" style="animation-delay: 0.05s"></div>
          <div class="eq-bar" style="animation-delay: 0.25s"></div>
          <div class="eq-bar" style="animation-delay: 0.18s"></div>
        </div>

        <div class="reel" id="right-reel">
          <div class="reel-center">
            <div class="reel-hole"></div>
          </div>
          <div class="spoke" style="transform: translate(-50%, 0) rotate(0deg)"></div>
          <div class="spoke" style="transform: translate(-50%, 0) rotate(30deg)"></div>
          <div class="spoke" style="transform: translate(-50%, 0) rotate(60deg)"></div>
          <div class="spoke" style="transform: translate(-50%, 0) rotate(90deg)"></div>
          <div class="spoke" style="transform: translate(-50%, 0) rotate(120deg)"></div>
          <div class="spoke" style="transform: translate(-50%, 0) rotate(150deg)"></div>
          <div class="tape-teeth"></div>
        </div>
      </div>

      <div class="tape-label" id="label">JAMES MATTHEW ALSTON</div>
    </div>

    <div class="progress-container">
      <div class="progress-bar" id="progress-bar">
        <div class="progress-fill" id="progress-fill"></div>
      </div>
      <div class="time-display">
        <span id="current-time">0:00</span>
        <span id="duration">0:00</span>
      </div>
    </div>

    <div class="controls">
      <button class="btn play-btn" id="play-btn">▶</button>
      <button class="btn stop-btn" id="stop-btn">■</button>
    </div>
  </div>
</div>

<audio id="audio"></audio>

<script>
const tracks = [
  { id: 1, title: 'Brother', src: '/assets/downloadmusic/brother.mp3' },
  { id: 2, title: 'Numb', src: '/assets/downloadmusic/numb.mp3' }
];

let currentTrack = null;
let isPlaying = false;

const audio = document.getElementById('audio');
const deck = document.getElementById('deck');
const trackList = document.getElementById('track-list');
const nowPlaying = document.getElementById('now-playing');
const label = document.getElementById('label');
const playBtn = document.getElementById('play-btn');
const stopBtn = document.getElementById('stop-btn');
const currentTimeEl = document.getElementById('current-time');
const durationEl = document.getElementById('duration');
const leftReel = document.getElementById('left-reel');
const rightReel = document.getElementById('right-reel');
const eqBars = document.querySelectorAll('.eq-bar');
const progressBar = document.getElementById('progress-bar');
const progressFill = document.getElementById('progress-fill');

tracks.forEach((track, i) => {
  const div = document.createElement('div');
  div.className = 'track-item';
  div.dataset.id = track.id;
  div.textContent = `${i + 1}. ${track.title}`;
  div.onclick = () => loadTrack(track);
  trackList.appendChild(div);
});

function loadTrack(track) {
  currentTrack = track;
  audio.src = track.src;
  deck.classList.add('active');
  nowPlaying.textContent = `♫ NOW PLAYING: ${track.title} ♫`;
  label.textContent = `JAMES MATTHEW ALSTON - ${track.title}`;
  
  document.querySelectorAll('.track-item').forEach(el => {
    el.classList.remove('active');
    if (el.dataset.id == track.id) el.classList.add('active');
  });

  setTimeout(() => {
    audio.play();
    setPlaying(true);
  }, 100);
}

playBtn.onclick = () => {
  if (!currentTrack) return;
  if (isPlaying) {
    audio.pause();
    setPlaying(false);
  } else {
    audio.play();
    setPlaying(true);
  }
};

stopBtn.onclick = () => {
  audio.pause();
  audio.currentTime = 0;
  setPlaying(false);
};

progressBar.onclick = (e) => {
  if (!currentTrack) return;
  const rect = progressBar.getBoundingClientRect();
  const percent = (e.clientX - rect.left) / rect.width;
  audio.currentTime = percent * audio.duration;
};

function setPlaying(playing) {
  isPlaying = playing;
  playBtn.textContent = playing ? '❚❚' : '▶';
  
  if (playing) {
    leftReel.classList.add('spinning');
    rightReel.classList.add('spinning');
    eqBars.forEach(bar => bar.classList.add('active'));
  } else {
    leftReel.classList.remove('spinning');
    rightReel.classList.remove('spinning');
    eqBars.forEach(bar => bar.classList.remove('active'));
  }
}

function formatTime(seconds) {
  if (isNaN(seconds)) return '0:00';
  const mins = Math.floor(seconds / 60);
  const secs = Math.floor(seconds % 60);
  return `${mins}:${secs.toString().padStart(2, '0')}`;
}

audio.ontimeupdate = () => {
  currentTimeEl.textContent = formatTime(audio.currentTime);
  const percent = (audio.currentTime / audio.duration) * 100;
  progressFill.style.width = percent + '%';
};

audio.onloadedmetadata = () => {
  durationEl.textContent = formatTime(audio.duration);
};

audio.onended = () => setPlaying(false);
</script>

</body>
</html>

<br>
<a href="https://washrooms.bandcamp.com/album/buried">Download on Bandcamp</a>
</div>