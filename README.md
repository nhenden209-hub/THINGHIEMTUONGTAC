<!DOCTYPE html>
<html lang="vi">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Mô Phỏng Chuyển Động Trái Đất</title>

<style>
/* === GIỮ NGUYÊN TOÀN BỘ CSS CỦA BẠN === */
/* (Mình không thay đổi CSS để tránh phá giao diện) */
</style>
</head>

<body>

<h2>Mô Phỏng Chuyển Động Trái Đất</h2>
<div class="subtitle">Quan sát tại 16°00′N 108°00′E (Việt Nam)</div>

<!-- ===== GIỮ NGUYÊN TOÀN BỘ HTML BODY CỦA BẠN ===== -->
<!-- (Phần này bạn copy y nguyên từ code cũ) -->

<script>
document.addEventListener("DOMContentLoaded", () => {

  let angle = 90;
  let isPlaying = false;
  let animFrame = null;

  const earthOrbit = document.getElementById("earthOrbit");
  const shadowOverlay = document.getElementById("shadowOverlay");
  const slider = document.getElementById("mainSlider");
  const btnPlay = document.getElementById("btnPlay");
  const statusMessage = document.getElementById("statusMessage");

  const seasonText = document.getElementById("seasonText");
  const seasonDesc = document.getElementById("seasonDesc");
  const seasonIndicator = document.getElementById("seasonIndicator");
  const dayBar = document.getElementById("dayBar");
  const dayHoursText = document.getElementById("dayHours");
  const nightHoursText = document.getElementById("nightHours");

  function updateSim(val) {
    angle = Number(val);
    const rad = angle * Math.PI / 180;

    earthOrbit.style.left = (50 + 45 * Math.cos(rad)) + "%";
    earthOrbit.style.top  = (50 - 45 * Math.sin(rad)) + "%";

    shadowOverlay.style.transform = `rotate(${angle + 90}deg)`;

    const variation = 1.3 * Math.cos(rad);
    const dayLength = 12 - variation;
    const nightLength = 24 - dayLength;

    dayHoursText.textContent = dayLength.toFixed(1) + "h";
    nightHoursText.textContent = nightLength.toFixed(1) + "h";
    dayBar.style.width = (dayLength / 24 * 100) + "%";

    seasonIndicator.style.left = (angle / 360 * 100) + "%";

    if (angle > 80 && angle < 100) {
      seasonText.textContent = "Xuân Phân (21/3)";
      seasonDesc.textContent = "Ngày = Đêm";
      seasonText.style.color = "#84CC16";
    } else if (angle < 170) {
      seasonText.textContent = "Mùa Hè";
      seasonDesc.textContent = "Ngày dài hơn Đêm";
      seasonText.style.color = "#EF4444";
    } else if (angle < 190) {
      seasonText.textContent = "Hạ Chí (22/6)";
      seasonDesc.textContent = "Ngày dài nhất";
      seasonText.style.color = "#EF4444";
    } else if (angle < 260) {
      seasonText.textContent = "Mùa Thu";
      seasonDesc.textContent = "Ngày ngắn dần";
      seasonText.style.color = "#FBBF24";
    } else if (angle < 280) {
      seasonText.textContent = "Thu Phân (23/9)";
      seasonDesc.textContent = "Ngày = Đêm";
      seasonText.style.color = "#FBBF24";
    } else if (angle < 350) {
      seasonText.textContent = "Mùa Đông";
      seasonDesc.textContent = "Đêm dài hơn Ngày";
      seasonText.style.color = "#3B82F6";
    } else {
      seasonText.textContent = "Đông Chí (22/12)";
      seasonDesc.textContent = "Đêm dài nhất";
      seasonText.style.color = "#3B82F6";
    }
  }

  function loop() {
    if (!isPlaying) return;

    angle += 0.5;
    if (angle >= 360) angle = 0;

    slider.value = angle;
    updateSim(angle);

    if (
      Math.abs(angle - 90) < 0.3 ||
      Math.abs(angle - 180) < 0.3 ||
      Math.abs(angle - 270) < 0.3 ||
      Math.abs(angle - 360) < 0.3
    ) {
      stop();
      statusMessage.textContent = "⏸ Tự động dừng để quan sát";
      return;
    }

    animFrame = requestAnimationFrame(loop);
  }

  function start() {
    isPlaying = true;
    btnPlay.textContent = "Dừng";
    btnPlay.classList.remove("paused");
    statusMessage.textContent = "";
    loop();
  }

  function stop() {
    isPlaying = false;
    cancelAnimationFrame(animFrame);
    btnPlay.textContent = "Tiếp tục";
    btnPlay.classList.add("paused");
  }

  slider.addEventListener("input", e => updateSim(e.target.value));
  btnPlay.addEventListener("click", () => isPlaying ? stop() : start());

  updateSim(angle);
});
</script>

</body>
</html>
