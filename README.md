# Heart
Đếm ngày yêu
![Hminh](https://user-images.githubusercontent.com/125713944/219829260-af5b68b6-ca23-4e5a-8e48-38ca1946ea89.jpg)
![Mia](https://user-images.githubusercontent.com/125713944/219829269-2d3bce6d-ab0b-4c8b-80c7-5b36681e355b.jpg)
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
</body>
</html>
html, body {
      background-color: #f6f6f6;
      margin: 0;
      padding: 0;
}

img {max-width: 100%;}

body {
      display: grid;
      font-family: "Segoe UI", sans-serif;
      grid-template-columns: repeat(12, 1fr);
      grid-auto-rows: minmax(auto, auto);
      color: #3e3e3e;
      text-shadow: 0.4px 0.4px 0.4px rgba(0,0,0,.2);
}

h1 {
      font-weight: lighter;
      grid-column: span 3;
      text-align: center;
      color: #ec407a;
}

#wrapper {
      display: grid;
      grid-column: 3 / 11;
      grid-template-columns: repeat(3, 1fr);
      grid-auto-rows: minmax(auto, auto);
      grid-row-gap: 10px;
      margin-top: 3.6rem;
}

#clock-box, #info {
      grid-column: span 3;
      display: grid;
      grid-template-columns: repeat(12, 1fr);
}

#clock-box #clock {
      grid-column: 4 / 10;
      background-color: #F8C8C8;
      padding: .6rem 2rem;
      padding-top: .8rem;
      text-align: center;
      font-size: 2.4rem;
      border-radius: 10rem;
}

date, time {
      display: block;
}

date {
      font-size: 18px;
}

time {
      font-family: "Arial", sans-serif;
      line-height: 3.2rem;
      letter-spacing: 2px;
}

.avt {
      width: 160px;
      height: 160px;
      border-radius: 50%;
      box-shadow: 2px 2px 8px rgba(0,0,0,.2);
}

#info {
      margin-top: 2.6rem;
}

#heart {
      grid-column: span 2;
      display: grid;
      grid-template-rows: 2;
      font-size: 44px;
      color: #b90d46;
      align-self: center;
      padding-bottom: 2.6rem;
      text-align: center;
}

anni {
      font-size: 16px;
      letter-spacing: 0.2px;
}

#info .one {
      grid-column: 3 / 6;
      text-align: center;
}

#info .two {
      grid-column: 8 / 11;
      text-align: center;
}

footer {
      grid-column: span 3;
      text-align: center;
      font-size: 1.6rem;
      font-weight: lighter;
      margin-top: 1.2rem;
}

#music {
      grid-column: 2;
      position: relative;
      z-index: 1000;
      opacity: .4;
}

#mask {
      background-image: linear-gradient(to top, #6d44cc5d 0%, #f09cd880 100%);
      opacity: .42;
      width: 100vw;
      height: 100vh;
      position: fixed;
      top: 0;
      left: 0;
}

@media (max-width: 992px) {
      #wrapper {
            grid-column: span 12;
      }

      #clock-box #clock {
            grid-column: 2 / 12;
      }

      .avt {
            width: 120px;
            height: 120px;
      }

      #info .one, #info .two{
            grid-column: span 12;;
      }

      #heart {
            grid-column: span 12;
            padding-bottom: 1rem;
      }

      footer {
            font-size: 1.2rem;
            margin: 0;
            padding-bottom: 2rem;
      }
}
