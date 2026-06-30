# PERSIA-DEBUT-STREAM
PERSIA DEBUT STREAM COUNTDOWN
<!DOCTYPE html>
<html lang="uz">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>4 Yillik Countdown</title>

<style>
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
}

body{
    background:#0f172a;
    color:white;
    font-family:Arial,sans-serif;
    display:flex;
    justify-content:center;
    align-items:center;
    height:100vh;
}

.container{
    text-align:center;
}

h1{
    margin-bottom:30px;
    font-size:40px;
}

.timer{
    display:flex;
    gap:20px;
    justify-content:center;
    flex-wrap:wrap;
}

.box{
    background:#1e293b;
    padding:20px;
    border-radius:15px;
    min-width:120px;
}

.box span{
    display:block;
    font-size:50px;
    font-weight:bold;
}

.box p{
    margin-top:10px;
    font-size:18px;
    color:#94a3b8;
}
</style>
</head>
<body>

<div class="container">
<h1>⏳ 4 Yillik Countdown</h1>

<div class="timer">
    <div class="box">
        <span id="days">0</span>
        <p>Kun</p>
    </div>

    <div class="box">
        <span id="hours">0</span>
        <p>Soat</p>
    </div>

    <div class="box">
        <span id="minutes">0</span>
        <p>Daqiqa</p>
    </div>

    <div class="box">
        <span id="seconds">0</span>
        <p>Soniya</p>
    </div>
</div>

</div>

<script>
const targetDate = new Date();
targetDate.setFullYear(targetDate.getFullYear() + 4);

function updateCountdown(){

    const now = new Date().getTime();
    const distance = targetDate.getTime() - now;

    if(distance <= 0){
        document.querySelector(".container").innerHTML =
        "<h1>🎉 Countdown Tugadi!</h1>";
        return;
    }

    const days = Math.floor(distance / (1000*60*60*24));
    const hours = Math.floor((distance % (1000*60*60*24))/(1000*60*60));
    const minutes = Math.floor((distance % (1000*60*60))/(1000*60));
    const seconds = Math.floor((distance % (1000*60))/1000);

    document.getElementById("days").textContent = days;
    document.getElementById("hours").textContent = hours;
    document.getElementById("minutes").textContent = minutes;
    document.getElementById("seconds").textContent = seconds;
}

updateCountdown();
setInterval(updateCountdown,1000);
</script>

</body>
</html>
