---
layout: default
title: 这里是易安和朱敬璞的点点滴滴
description: 爱你哟宝贝😚😚😚
---
<style>
  body {
    background-image: url('/assets/images/background.jpg'); /* 替换成你的图片路径 */
    background-size: cover;
    background-position: center;
    background-attachment: fixed;
    background-repeat: no-repeat;
    color: white; /* 如果背景图较暗，可以让字体变白 */
  }

  nav a {
    color: white;
    font-weight: bold;
  }

  button {
    background-color: rgba(255, 255, 255, 0.7);
    border: none;
    padding: 8px 12px;
    margin: 5px;
    border-radius: 5px;
    cursor: pointer;
  }

  button:hover {
    background-color: rgba(255, 255, 255, 0.9);
  }
</style>

<nav>
  <a href="/">首页</a> |
  <a href="/photos">咱俩的照片</a> |
  <a href="/story">咱俩的故事</a> |
  <a href="/future">咱俩的畅想</a>
</nav>

<p><em>记得要新标签页打开喔！</em></p>

# 👋 欢迎来到我们的网站！

**好喜欢好喜欢好喜欢宝贝！**

<p>🔊 放点歌听听？🔊</p>
<button onclick="playMusic()">点我播放各种应景的小情歌</button>

<p id="now-playing" style="font-weight: bold; margin-top: 10px;"></p>

<audio id="bgm" autoplay controls></audio>
<button onclick="nextSong()">换一首</button>

<script>
  const playlist = [
    { src: '/assets/music/bgm1.mp3', title: '红豆 - 方大同' },
    { src: '/assets/music/bgm2.mp3', title: '就是爱你 - 陶喆' },
    { src: '/assets/music/bgm3.mp3', title: '永恒的主题 - 丁世光' }
  ];

  let currentTrack = 0;
  const player = document.getElementById('bgm');
  const nowPlaying = document.getElementById('now-playing');

  function updateNowPlaying() {
    nowPlaying.innerText = '正在播放：' + playlist[currentTrack].title;
  }

  function playMusic() {
    player.src = playlist[currentTrack].src;
    updateNowPlaying();
    player.play();
  }

  function nextSong() {
    currentTrack = (currentTrack + 1) % playlist.length;
    playMusic();
  }

  player.addEventListener('ended', nextSong);
</script>


