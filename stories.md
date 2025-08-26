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
  body {
    margin: 0;
    overflow: hidden; /* 防止超出滚动条 */
  }

  /* 容器全屏 */
  .story-container {
    position: relative;
    width: 100vw;
    height: 100vh;
    overflow: hidden;
  }

  /* 链接样式 */
  .story-link {
    position: absolute;
    font-size: 18px;
    font-weight: bold;
    text-decoration: none;
    white-space: pre-line;
    transition: transform 0.3s ease, color 0.3s ease;
    animation: floatXY linear infinite;
  }

  .story-link:hover {
    transform: scale(1.2);
  }

  /* 定义XY方向漂浮 */
  @keyframes floatXY {
    0% { transform: translate(0px, 0px); }
    25% { transform: translate(30px, -20px); }
    50% { transform: translate(-20px, 30px); }
    75% { transform: translate(20px, -30px); }
    100% { transform: translate(0px, 0px); }
  }
</style>

<div class="story-container" id="storyContainer">
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
  const links = document.querySelectorAll('.story-link');
  const colors = ['#ff6699', '#ffcc66', '#66ccff', '#99ff66', '#cc99ff'];

  links.forEach(link => {
    // 随机位置
    const top = Math.random() * 80 + 10;   // 避免贴边
    const left = Math.random() * 80 + 10;
    link.style.top = top + 'vh';
    link.style.left = left + 'vw';

    // 随机颜色
    link.style.color = colors[Math.floor(Math.random() * colors.length)];

    // 随机动画时长
    const duration = Math.random() * 10 + 5; // 5-15秒
    link.style.animationDuration = duration + 's';
  });
</script>


