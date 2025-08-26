---
layout: default
title: 咱俩的故事
permalink: /stories/
---

<nav>
  <a href="/">首页</a> |
  <a href="/photos">咱俩的照片</a> |
  <a href="/stories">咱俩的故事</a> |
  <a href="/future">咱俩的畅想</a> |
  <a href="/love">我爱你什么</a> |
</nav>

<style>
  .story-container {
    position: relative;
    width: 100%;
    height: 80vh;
    overflow: hidden;
  }

  .story-link {
    position: absolute;
    font-size: 18px;
    font-weight: bold;
    text-decoration: none;
    white-space: pre-line;
    transition: transform 0.3s ease, color 0.3s ease;
  }

  .story-link:hover {
    transform: scale(1.2);
  }

  /* 定义多种颜色 */
  .color1 { color: #ff6699; }
  .color2 { color: #3399ff; }
  .color3 { color: #9933ff; }
  .color4 { color: #ff9933; }
  .color5 { color: #33cc99; }

  /* 漂浮动画 - 上下 */
  @keyframes floatY {
    0% { transform: translateY(0); }
    50% { transform: translateY(-30px); }
    100% { transform: translateY(0); }
  }

  /* 漂浮动画 - 左右 */
  @keyframes floatX {
    0% { transform: translateX(0); }
    50% { transform: translateX(30px); }
    100% { transform: translateX(0); }
  }

  /* 漂浮动画 - 斜向 */
  @keyframes floatXY {
    0% { transform: translate(0, 0); }
    50% { transform: translate(20px, -20px); }
    100% { transform: translate(0, 0); }
  }
</style>

<div class="story-container">
  <a href="/story1" class="story-link">
    不知道该怎么说<br>
    感谢的话这么多<br>
    你就像是救了我<br>
    在广阔寂寞漩涡解脱<br>
    感谢上天结果<br>
    管结果 是对 是错 是福 是祸<br>
    使我 对爱再没那么多疑惑<br>
    ——《麦恩莉》 方大同
  </a>

  <a href="/story2" class="story-link">
    春天是她最爱的季节<br>
    当微风随意吹乱她的头发<br>
    ——《二十二》陶喆
  </a>

  <a href="/story3" class="story-link">
    原谅我最近在低潮期<br>
    有些话我讲的不好听<br>
    可能因为实在太熟悉<br>
    下意识对你像对我自己<br>
    ——《低潮期》丁世光
  </a>

  <a href="/story4" class="story-link">
    故乡哟故乡<br>
    爱人哟爱人<br>
    既然都忘不掉<br>
    不如就装着吧<br>
    ——《道别是一件难事》上海彩虹室内合唱团
  </a>
</div>

<script>
  document.querySelectorAll('.story-link').forEach(link => {
    // 随机位置 (10%-80%)
    let top = Math.random() * 70 + 10;
    let left = Math.random() * 70 + 10;
    link.style.top = top + '%';
    link.style.left = left + '%';

    // 随机颜色
    let colors = ['color1', 'color2', 'color3', 'color4', 'color5'];
    link.classList.add(colors[Math.floor(Math.random() * colors.length)]);

    // 随机漂浮方向
    let animations = ['floatY', 'floatX', 'floatXY'];
    let anim = animations[Math.floor(Math.random() * animations.length)];
    let duration = Math.random() * 5 + 6; // 6-11秒
    link.style.animation = `${anim} ${duration}s ease-in-out infinite`;
  });
</script>

