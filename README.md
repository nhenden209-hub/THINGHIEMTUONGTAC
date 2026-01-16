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
<!DOCTYPE html>
<html lang="vi">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Bài giảng Địa lí – Tự nhiên</title>

<style>
body{
    font-family: Arial, sans-serif;
    margin:0;
    background:#0f172a;
    color:#e5e7eb;
}
header{
    background:#020617;
    padding:10px;
    text-align:center;
    font-weight:bold;
}
nav{
    display:flex;
    gap:8px;
    padding:10px;
    overflow-x:auto;
    background:#020617;
}
nav button{
    flex:0 0 auto;
    padding:8px 12px;
    border:none;
    border-radius:6px;
    background:#1e293b;
    color:white;
    font-size:14px;
}
nav button.active{
    background:#38bdf8;
    color:black;
}
section{
    display:none;
    padding:15px;
}
section.active{
    display:block;
}
.box{
    background:#1e293b;
    padding:15px;
    border-radius:10px;
    margin-bottom:15px;
}
.orbit{
    width:200px;
    height:200px;
    border:1px dashed #64748b;
    border-radius:50%;
    position:relative;
    margin:auto;
}
.sun{
    width:30px;
    height:30px;
    background:gold;
    border-radius:50%;
    position:absolute;
    top:50%;
    left:50%;
    transform:translate(-50%,-50%);
}
.earth{
    width:14px;
    height:14px;
    background:#38bdf8;
    border-radius:50%;
    position:absolute;
    top:-7px;
    left:50%;
    transform:translateX(-50%);
}
.globe{
    width:180px;
    height:180px;
    border-radius:50%;
    background:radial-gradient(circle at 30% 30%,#38bdf8,#1e3a8a);
    margin:auto;
    position:relative;
}
.axis{
    position:absolute;
    top:-20px;
    bottom:-20px;
    left:50%;
    width:2px;
    background:white;
    transform:rotate(-23.5deg);
}
.wave{
    height:20px;
    background:linear-gradient(90deg,#38bdf8,#0ea5e9);
    border-radius:10px;
    animation:wave 2s infinite linear;
}
@keyframes wave{
    0%{transform:translateX(0)}
    100%{transform:translateX(-50px)}
}
</style>
</head>

<body>

<header>BÀI GIẢNG ĐỊA LÍ – TỰ NHIÊN</header>

<nav>
<button onclick="show(0)" class="active">Trái Đất quanh Mặt Trời</button>
<button onclick="show(1)">Trái Đất tự quay</button>
<button onclick="show(2)">Núi lửa</button>
<button onclick="show(3)">Sóng biển</button>
<button onclick="show(4)">Thủy triều</button>
</nav>

<section class="active">
<div class="box">
<h3>Trái Đất chuyển động quanh Mặt Trời</h3>
<div class="orbit" id="orbit">
<div class="sun"></div>
<div class="earth" id="earth"></div>
</div>
<p>→ Gây ra các mùa trong năm.</p>
</div>
</section>

<section>
<div class="box">
<h3>Trái Đất tự quay quanh trục</h3>
<div class="globe">
<div class="axis"></div>
</div>
<p>→ Gây ra hiện tượng ngày và đêm.</p>
</div>
</section>

<section>
<div class="box">
<h3>Núi lửa</h3>
<p>Núi lửa hình thành do macma từ sâu trong lòng đất phun trào.</p>
</div>
</section>

<section>
<div class="box">
<h3>Sóng biển</h3>
<div class="wave"></div>
<p>Sóng biển chủ yếu do gió tạo ra.</p>
</div>
</section>

<section>
<div class="box">
<h3>Thủy triều</h3>
<p>Thủy triều do lực hút của Mặt Trăng và Mặt Trời.</p>
</div>
</section>

<script>
let angle=0;
setInterval(()=>{
    angle+=1;
    document.getElementById("earth").style.transform=
        "rotate("+angle+"deg) translateX(-50%)";
},60);

function show(i){
    document.querySelectorAll("section").forEach(s=>s.classList.remove("active"));
    document.querySelectorAll("nav button").forEach(b=>b.classList.remove("active"));
    document.querySelectorAll("section")[i].classList.add("active");
    document.querySelectorAll("nav button")[i].classList.add("active");
}
</script>

</body>
</html>
