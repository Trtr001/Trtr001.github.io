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
  /* 整个容器 */
  .story-container {
    position: relative;
    width: 100%;
    height: 80vh;
    overflow: hidden;
  }

  /* 每个歌词链接的样式 */
  .story-link {
    position: absolute;
    font-size: 18px;
    color: #ff6699;
    text-decoration: none;
    font-weight: bold;
    white-space: pre-line; /* 保留歌词的换行 */
    transition: transform 0.3s ease, color 0.3s ease;
  }

  .story-link:hover {
    transform: scale(1.2);
    color: #ff3366;
  }

  /* 加个缓慢浮动的动画效果 */
  @keyframes float {
    0% { transform: translateY(0px); }
    50% { transform: translateY(-20px); }
    100% { transform: translateY(0px); }
  }
</style>

<div class="story-container">
  <a href="/story1" class="story-link" style="top:10%; left:20%; animation: float 6s ease-in-out infinite;">
    不知道该怎么说<br>
    感谢的话这么多<br>
    你就像是救了我<br>
    在广阔寂寞漩涡解脱<br>
    感谢上天结果<br>
    管结果 是对 是错 是福 是祸<br>
    使我 对爱再没那么多疑惑<br>
    ——《麦恩莉》 方大同
  </a>

  <a href="/story2" class="story-link" style="top:40%; left:60%; animation: float 8s ease-in-out infinite;">
    春天是她最爱的季节<br>
    当微风随意吹乱她的头发<br>
    ——《二十二》陶喆
  </a>

  <a href="/story3" class="story-link" style="top:70%; left:30%; animation: float 10s ease-in-out infinite;">
    原谅我最近在低潮期<br>
    有些话我讲的不好听<br>
    可能因为实在太熟悉<br>
    下意识对你像对我自己<br>
    ——《低潮期》丁世光
  </a>

  <a href="/story4" class="story-link" style="top:50%; left:80%; animation: float 7s ease-in-out infinite;">
    故乡哟故乡<br>
    爱人哟爱人<br>
    既然都忘不掉<br>
    不如就装着吧<br>
    ——《道别是一件难事》上海彩虹室内合唱团
  </a>
</div>
