---
layout: default
title: 这里是易安和朱敬璞的点点滴滴
description: 爱你哟宝贝😚😚😚
---

<nav>
  <a href="/">首页</a> |
  <a href="/photos">咱俩的照片</a> |
  <a href="/story">咱俩的故事</a> |
  <a href="/future">咱俩的畅想</a>
</nav>

<p><em>记得要新标签页打开喔！</em></p>

<p>🔊 放点歌听听？🔊</p>
<button onclick="playMusic()">点我播放各种应景的小情歌</button>

<audio id="bgm" autoplay controls></audio>

<script>
  const playlist = [
    '/assets/music/bgm1.mp3',
    '/assets/music/bgm2.mp3',
    '/assets/music/bgm3.mp3'
  ];
  let currentTrack = 0;
  const player = document.getElementById('bgm');

  function playMusic() {
    player.src = playlist[currentTrack];
    player.play();
  }

  player.addEventListener('ended', () => {
    currentTrack = (currentTrack + 1) % playlist.length;
    player.src = playlist[currentTrack];
    player.play();
  });
</script>

# 👋 欢迎来到我们的网站！

**好喜欢好喜欢好喜欢宝贝！**
