# Heart
Đếm ngày yêu
<!DOCTYPE html>
<html lang="en">
<head>
      <meta charset="UTF-8">
      <meta name="viewport" content="width=device-width, initial-scale=1.0">
      <meta http-equiv="X-UA-Compatible" content="ie=edge">
      <link rel="stylesheet" href="style.css">
      <link rel="shortcut icon" type="image/png" href="img/favicon.png"/>
      <title>Together</title>
</head>
<body>
     <div id="wrapper">
           <h1>LOVE DAYS</h1>

           <div id="clock-box">
                 <div id="clock">
                       <date>0 DAYS</date>
                       <time>00:00:00</time>
                  </div>
            </div>
            
            <div id="info">
                  <div class="one">
                        <img src="img/Mia.jpg" class="avt">
                        <p>Mia Đáng Iu <3</p>
                  </div>
                  <div id="heart">
                        ❤<anni>...</anni>
                  </div>
                  <div class="two">
                        <img src="img/Hminh.jpg" class="avt">
                        <p>LHMinh</p>
                  </div>
            </div>
            
            <div id="music">
                  <audio loop autoplay controls>Your browser does not support the audio element.</audio>
            </div>
            <footer>Thank you for your love 💕</footer>
      </div> 
      
      <script src="app.js"></script>
      const yourDate = new Date("2022-11-18T20:00:00"),
music = ['ido'];

document.addEventListener('DOMContentLoaded', function(){
      var rootTime = document.querySelector("time");

      document.querySelector("anni").textContent = `${(yourDate.getDate()>9)?yourDate.getDate():"0"+yourDate.getDate()}-${(yourDate.getMonth()>8)?(yourDate.getMonth()+1):"0"+(yourDate.getMonth()+1)}-${yourDate.getFullYear()}`;
      
      document.querySelector("date").textContent = Math.floor( Math.floor((new Date() - yourDate) / 1000) / 60 / 60 / 24)+" DAYS";

      function olock() {
            var today = new Date(),
            hrs = (Math.floor( Math.floor((today - yourDate) / 1000) / 60 / 60)) % 24,
            min = (Math.floor( Math.floor((today - yourDate) / 1000) / 60)) % 60,
            sec =  Math.floor((today - yourDate) / 1000) % 60;
            rootTime.textContent = `${(hrs>9)?hrs:"0"+hrs}:${(min>9)?min:"0"+min}:${(sec>9)?sec:"0"+sec}`;
      } olock();
      var timer = setInterval(function(){olock()}, 1000);
      document.querySelector("audio").setAttribute("src", `music/${music[Math.floor(Math.random()*music.length)]}.mp3`);

      document.getElementsByTagName("body")[0].insertAdjacentHTML(
            "beforeend",
            "<div id='mask'></div>"
      );

}, false);
