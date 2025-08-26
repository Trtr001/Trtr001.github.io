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
    overflow: hidden;
  }
  .story-container {
    position: relative;
    width: 100vw;
    height: 100vh;
    overflow: hidden;
  }
  .story-link {
    position: absolute;
    font-size: 18px;
    font-weight: bold;
    text-decoration: none;
    white-space: pre-line;
    transition: transform 0.3s ease;
  }
  .story-link:hover {
    transform: scale(1.2);
  }
</style>

<div class="story-container" id="storyContainer">
  <a href="/story1" class="story-link">
    不知道该怎么说<br>
    感谢的话这么多<br>
    你就像是救了我<br>
    在广阔寂寞漩涡解脱<br>
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
    ——《低潮期》丁世光
  </a>
  <a href="/story4" class="story-link">
    故乡哟故乡<br>
    爱人哟爱人<br>
    ——《道别是一件难事》上海彩虹室内合唱团
  </a>
</div>

<script>
  const container = document.getElementById("storyContainer");
  const links = document.querySelectorAll(".story-link");
  const colors = ['#ff6699', '#ffcc66', '#66ccff', '#99ff66', '#cc99ff'];

  links.forEach(link => {
    // 随机初始位置 (考虑元素尺寸)
    const rect = container.getBoundingClientRect();
    const linkRect = link.getBoundingClientRect();
    const maxX = rect.width - linkRect.width - 20;
    const maxY = rect.height - linkRect.height - 20;

    const x = Math.random() * maxX;
    const y = Math.random() * maxY;

    link.style.left = x + "px";
    link.style.top = y + "px";

    // 随机颜色
    link.style.color = colors[Math.floor(Math.random() * colors.length)];

    // 随机速度和方向
    link.dataset.vx = (Math.random() * 1 + 0.3) * (Math.random() < 0.5 ? 1 : -1);
    link.dataset.vy = (Math.random() * 1 + 0.3) * (Math.random() < 0.5 ? 1 : -1);
  });

  function animate() {
    links.forEach(link => {
      const rect = container.getBoundingClientRect();
      const linkRect = link.getBoundingClientRect();
      let x = parseFloat(link.style.left);
      let y = parseFloat(link.style.top);
      let vx = parseFloat(link.dataset.vx);
      let vy = parseFloat(link.dataset.vy);

      // 移动
      x += vx;
      y += vy;

      // 边界检测，反弹
      if (x <= 0 || x + linkRect.width >= rect.width) vx *= -1;
      if (y <= 0 || y + linkRect.height >= rect.height) vy *= -1;

      link.style.left = Math.max(0, Math.min(rect.width - linkRect.width, x)) + "px";
      link.style.top = Math.max(0, Math.min(rect.height - linkRect.height, y)) + "px";

      link.dataset.vx = vx;
      link.dataset.vy = vy;
    });
    requestAnimationFrame(animate);
  }

  animate();
</script>



