<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>卡密验证</title>
<style>
*{margin:0;padding:0;box-sizing:border-box;}
body{background:#f5f5f5;font-family:Arial;display:flex;align-items:center;justify-content:center;height:100vh;}
.box{background:#fff;padding:30px;border-radius:8px;box-shadow:0 0 10px #eee;width:90%;max-width:400px;}
h2{text-align:center;margin-bottom:30px;color:#333;}
input{width:100%;padding:12px 15px;border:1px solid #ddd;border-radius:6px;font-size:16px;margin-bottom:20px;}
button{width:100%;padding:12px;background:#007bff;color:#fff;border:none;border-radius:6px;font-size:16px;cursor:pointer;}
button:hover{background:#0056b3;}
.msg{margin-top:20px;text-align:center;font-size:16px;}
</style>
</head>
<body>
<div class="box">
    <h2>请输入卡密</h2>
    <input type="text" id="card" placeholder="输入卡密">
    <button onclick="check()">验证</button>
    <div class="msg" id="msg"></div>
</div>
<script>
// 这里改成你自己的卡密
const validCards = ["ABC123","DEF456","GHI789"];

function check(){
    const input = document.getElementById("card").value.trim();
    const msg = document.getElementById("msg");
    if(!input){
        msg.innerText = "请输入卡密";
        msg.style.color = "red";
        return;
    }
    if(validCards.includes(input)){
        msg.innerText = "✅ 验证成功！";
        msg.style.color = "green";
    }else{
        msg.innerText = "❌ 卡密无效";
        msg.style.color = "red";
    }
}
</script>
</body>
</html>