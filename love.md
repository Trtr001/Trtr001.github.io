---
layout: default
title: 这里陈列了各种我爱宝贝的点
description: 想到新的我还会补上的喔~
permalink: /love/
---

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
  text-align: center;
  font-family: "Segoe UI", "Comic Sans MS", cursive;
  
  /* 渐变文字 */
  background: linear-gradient(to right, #ff69b4, #dda0dd);
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
<button onclick="nextLoveNote()">换一句</button>

<script>
const loveNotes = [
  "我爱宝贝的眼睛，哭或笑的时候总是闪着惹人怜爱的光芒",
  "我爱宝贝的嘴唇，软软的甜甜的像一块让人垂涎欲滴的软糖",
  "我爱宝贝的睫毛，当我用脸蹭宝贝时，宝贝轻轻开合眼眸用睫毛挠我的脸",
  "我爱宝贝的头发，永远带着一股令我安心的香气",
  "我爱宝贝的脸颊，滑滑嫩嫩软软弹弹，我恨不得多长几张嘴来亲它",
  "我爱宝贝的脖颈和锁骨，每次看到宝贝我都忍不住凑过去探索它们",
  "我爱宝贝的舌尖，带着温润的液体和湿热的气息，我的心也被它给缠住了",
  "我爱宝贝的手，纤纤如细枝，温润如良玉，摩挲宝贝的手掌心我希望能传递出我心中的爱意",
  "我爱宝贝的指尖，它们从我的脸庞滑向我的胸膛时，我能感受到宝贝缠缠绵绵的爱",
  "我爱宝贝的肌肤，当我抚摸它时，总有一阵凉丝丝的清爽，但我更希望能给它带来温暖",
  "我爱宝贝的脊背，我用手抚摸时，宝贝便像受惊的猫一般扭动（好可爱(*╹▽╹*)）",
  "我爱宝贝的腰肢，当我用手环抱着它，我感觉世界都在我的怀抱中",
  "我爱宝贝的眼神，当它看向我时，投射出缠绵的依恋与爱欲，让我深深陷于其中",
  "我爱宝贝的笑，明媚又温和，像寒冬时节投向文德楼的阳光，给我带来阵阵暖意",
  "我爱宝贝的眼泪，当我第一次拭去宝贝眼角滑落的泪滴的那一刻，也代表我准备好接受宝贝所有的柔软",
  "我爱宝贝的舌尖，带着温润的液体和湿热的气息，我的心也被它给缠住了",
  "我爱宝贝的舌尖，带着温润的液体和湿热的气息，我的心也被它给缠住了",
  "我爱宝贝的舌尖，带着温润的液体和湿热的气息，我的心也被它给缠住了",
  "我爱宝贝的舌尖，带着温润的液体和湿热的气息，我的心也被它给缠住了",
  "我爱宝贝的舌尖，带着温润的液体和湿热的气息，我的心也被它给缠住了",
  "我爱宝贝的舌尖，带着温润的液体和湿热的气息，我的心也被它给缠住了",
  "我爱宝贝的舌尖，带着温润的液体和湿热的气息，我的心也被它给缠住了",
  "我爱宝贝的舌尖，带着温润的液体和湿热的气息，我的心也被它给缠住了",
  "我爱宝贝的舌尖，带着温润的液体和湿热的气息，我的心也被它给缠住了",
  "我爱宝贝的舌尖，带着温润的液体和湿热的气息，我的心也被它给缠住了",
  "我爱宝贝的舌尖，带着温润的液体和湿热的气息，我的心也被它给缠住了",
  "我爱宝贝的舌尖，带着温润的液体和湿热的气息，我的心也被它给缠住了",
  "我爱宝贝的舌尖，带着温润的液体和湿热的气息，我的心也被它给缠住了",
  "我爱宝贝的舌尖，带着温润的液体和湿热的气息，我的心也被它给缠住了",
  "我爱宝贝的舌尖，带着温润的液体和湿热的气息，我的心也被它给缠住了",
  "我爱宝贝的舌尖，带着温润的液体和湿热的气息，我的心也被它给缠住了",
  "我爱宝贝的舌尖，带着温润的液体和湿热的气息，我的心也被它给缠住了",
  "我爱宝贝的舌尖，带着温润的液体和湿热的气息，我的心也被它给缠住了",
  "我爱宝贝的舌尖，带着温润的液体和湿热的气息，我的心也被它给缠住了",
  "我爱宝贝的舌尖，带着温润的液体和湿热的气息，我的心也被它给缠住了",
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

