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
    const vx = (Math.random() * 1 + 0.3) * (Math.random() < 0.5 ? 1 : -1);
    const vy = (Math.random() * 1 + 0.3) * (Math.random() < 0.5 ? 1 : -1);

    link.dataset.vx = vx;
    link.dataset.vy = vy;
    link.dataset.originalVx = vx;
    link.dataset.originalVy = vy;

    // 悬停时暂停
    link.addEventListener("mouseover", () => {
      link.dataset.vx = 0;
      link.dataset.vy = 0;
    });

    // 移开时恢复
    link.addEventListener("mouseout", () => {
      link.dataset.vx = link.dataset.originalVx;
      link.dataset.vy = link.dataset.originalVy;
    });
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
      if (x <= 0 || x + linkRect.width >= rect.width) {
        vx *= -1;
        link.dataset.originalVx *= -1; // 更新原始方向
      }
      if (y <= 0 || y + linkRect.height >= rect.height) {
        vy *= -1;
        link.dataset.originalVy *= -1; // 更新原始方向
      }

      link.style.left = Math.max(0, Math.min(rect.width - linkRect.width, x)) + "px";
      link.style.top = Math.max(0, Math.min(rect.height - linkRect.height, y)) + "px";

      link.dataset.vx = vx;
      link.dataset.vy = vy;
    });
    requestAnimationFrame(animate);
  }

  animate();
</script>




