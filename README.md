<!DOCTYPE html>
<html lang="vi">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Bài giảng Địa lí – Tự nhiên</title>

<style>
*{box-sizing:border-box}
body{
    margin:0;
    font-family:Arial, Helvetica, sans-serif;
    background:#0f172a;
    color:#e5e7eb;
}
header{
    background:#020617;
    padding:12px;
    text-align:center;
    font-size:16px;
    font-weight:bold;
}
nav{
    display:flex;
    gap:8px;
    padding:10px;
    background:#020617;
    overflow-x:auto;
}
nav button{
    flex:0 0 auto;
    padding:8px 12px;
    border:none;
    border-radius:8px;
    background:#1e293b;
    color:white;
    font-size:14px;
}
nav button.active{
    background:#38bdf8;
    color:black;
    font-weight:bold;
}
section{
    display:none;
    padding:15px;
}
section.active{display:block}
.box{
    background:#1e293b;
    padding:15px;
    border-radius:12px;
    marg
