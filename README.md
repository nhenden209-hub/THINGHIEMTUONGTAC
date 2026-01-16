<!DOCTYPE html>
<html lang="vi">
<head>
<meta charset="UTF-8">

<!-- BẮT BUỘC CHO ĐIỆN THOẠI -->
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Mô phỏng Trái Đất</title>

<style>
:root {
  --bg-color: #020617;
  --panel-bg: #020617;
  --text-color: #E5E7EB;
  --sun-color: #FACC15;
  --highlight: #38BDF8;
  --day-color: #FDE047;
  --night-color: #020617;
  --equator-color: #F97316;
  --winter-cold: #38BDF8;
  --summer-hot: #EF4444;
}

* { box-sizing: border-box; }

body {
  margin: 0;
  font-family: system-ui, -apple-system, BlinkMacSystemFont, sans-serif;
  background: var(--bg-color);
  color: var(--text-color);
  display: flex;
  flex-direction: column;
  align-items: center;
}

/* TIÊU ĐỀ */
h2 {
  margin: 15px 0 5px;
  color: var(--sun-color);
  font-size: 1.2rem;
  text-align: center;
}

.subtitle {
  font-size: 0.9rem;
  color: #94A3B8;
  margin-bottom: 10px;
  text-align: center;
}

/* LAYOUT */
.dashboard {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 12px;
  width: 95%;
  max-width: 900px;
  padding: 12px;
}

/* PANEL */
.visual-panel {
  background: rgba(255,255,255,0.04);
  border-radius: 12px;
  height: 260px;
  display: flex;
  justify-content: center;
  align-items: center;
}

/* MOBILE: CHỈ 1 CỘT */
@media (max-width: 768px) {
  .dashboard {
    grid-template-columns: 1fr;
  }

  .visual-panel {
    height: 220px;
  }
}

/* GIẢM HIỆU ỨNG NẶNG */
.sun {
  width: 36px;
  height: 36px;
  background: radial-gradient(circle, #fff, var(--sun-color));
  border-radius: 50%;
}
</style>

</head>

<body>

<h2>MÔ PHỎNG CHUYỂN ĐỘNG TRÁI ĐẤT</h2>
<div class="subtitle">Xem tốt trên điện thoại</div>

<div class="dashboard">
  <div class="visual-panel">
    <div class="sun"></div>
  </div>
</div>

</body>
</html>
