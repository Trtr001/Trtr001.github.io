---
layout: default
title: 这里是我们对未来的各种愿望喔
description: 已经完成的就会在后面打上一个√
permalink: /future/
---

<nav>
  <a href="/">首页</a> |
  <a href="/photos">咱俩的照片</a> |
  <a href="/stories">咱俩的故事</a> |
  <a href="/future">咱俩的畅想</a> |
  <a href="/love">我爱你什么</a> |
</nav>

<style>
.love-note {
  width: 100%;
  border: none;
  background: none;
  resize: none;
  padding: 0;
  margin-bottom: 1.5em;
  font-size: 1.4em;
  line-height: 1.8;
  text-align: center; /* 居中 */
  font-family: "Segoe UI", "Comic Sans MS", cursive;
  
  /* 渐变文字 */
  background: linear-gradient(to right, #ff7eb3, #65c7f7, #0052d4); /* 新渐变色 */
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  
  /* 动画过渡 */
  transition: opacity 0.5s ease;
}
button {
  display: block;
  margin: 20px auto;
  padding: 10px 20px;
  font-size: 1.1em;
  border: none;
  border-radius: 8px;
  background: linear-gradient(45deg, #ff69b4, #dda0dd);
  color: white;
  cursor: pointer;
  transition: background 0.3s ease;
}
button:hover {
  background: linear-gradient(45deg, #dda0dd, #ff69b4);
}
</style>

<textarea id="loveText" class="love-note" readonly></textarea>
<button onclick="nextLoveNote()">换一个呢</button>

<script>
const loveNotes = [
  "一起爬山√",
  "一起半夜压马路√",
  "一起去重庆旅游",
  "一起看电影√",
  "一起有个小家",
  "养小猫小狗",
  "一起去玉龙雪山",
  "一起去云南",
  "一起去景德镇",
  "一起去游乐园",
  "一起做饭",
  "一起拼图√",
  "一起去看演唱会",
  "一起做手工√",
  "一起玩游戏√",
  "一起骑小电驴兜风",
  "一起在海边散步",
  "一起去网吧",
  "一起去唱歌√",
  "一起去酒吧",
  "一起戴戒指√",
  "穿情侣装√",
  "用拍立得记录我们√",
  "结婚",
  "订婚"
];

let currentIndex = -1;
const textArea = document.getElementById("loveText");

function nextLoveNote() {
  let newIndex;
  do {
    newIndex = Math.floor(Math.random() * loveNotes.length);
  } while (newIndex === currentIndex);
  
  currentIndex = newIndex;
  
  textArea.style.opacity = 0;
  setTimeout(() => {
    textArea.value = loveNotes[currentIndex];
    textArea.style.opacity = 1;
  }, 300);
}

// 初始化时显示一句
nextLoveNote();
</script>

