<template>
  <div id="app">

    <!-- heart -->
    <div class="heart-container">
        <div class="heart">
          <div class="heart-piece-0"></div>
          <div class="heart-piece-1"></div>
          <div class="heart-piece-2"></div>
          <div class="heart-piece-3"></div>
          <div class="heart-piece-4"></div>
          <div class="heart-piece-5"></div>
          <div class="heart-piece-6"></div>
          <div class="heart-piece-7"></div>
          <div class="heart-piece-8"></div>
        </div>
    </div>

    <!-- countdown -->
    <div class="countdown-container">
      <div id="countdown">
        <ul>
          <li><span id="days"></span>Days</li>
          <li><span id="hours"></span>Hours</li>
          <li><span id="minutes"></span>Minutes</li>
          <li><span id="seconds"></span>Seconds</li>
        </ul>
      </div>

      <div class="message">
        <div id="content">
          <span class="emoji">🎉</span>
          <span class="emoji">🎉</span>
          <span class="emoji">🎉</span>
        </div>
      </div>
    </div>

    <!-- love phrase  -->
    <div class="phrase-container">
      <div id="phrase">
        1st anniversary countdown with Arslan
      </div>
    </div>
  </div>
</template>

<script>

(function () {
  const second = 1000,
      minute = second * 60,
      hour = minute * 60,
      day = hour * 24;

  let birthday = "Nov 14, 2021 00:00:00",
      countDown = new Date(birthday).getTime(),
      x = setInterval(function() {

        let now = new Date().getTime(),
            distance = countDown - now;

        if (distance > 0) {
            document.getElementById("days").innerText = Math.floor(distance / (day)),
              document.getElementById("hours").innerText = Math.floor((distance % (day)) / (hour)),
              document.getElementById("minutes").innerText = Math.floor((distance % (hour)) / (minute)),
              document.getElementById("seconds").innerText = Math.floor((distance % (minute)) / second);

        } else {
          // when reach the day
          let phrase = document.getElementById("phrase"),
              countdown = document.getElementById("countdown"),
              content = document.getElementById("content");

          countdown.style.display = "none";
          phrase.innerText = "Dear Arslan, happy 1st anniversary!!!\nI love you forever~";
          content.style.display = "block";

          clearInterval(x);
        }

        //seconds
      }, 0)
}());
</script>

<style>

* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
  color: white;
}

html, body {
  height: 100%;
}

body {
  background-color: black;
  display: flex;
  align-items: center;
  justify-content: center;
}

.phrase-container {
  text-align: center;
}

.countdown-container {
  margin: 5rem auto 0.5rem;
  text-align: center;
}

li {
  display: inline-block;
  font-size: 1em;
  list-style-type: none;
  padding: 1em;
  text-transform: uppercase;
}

li span {
  display: block;
  font-size: 4rem;
}

.message {
  font-size: 2rem;
}

#content {
  display: none;
  padding: 1rem;
}

.emoji {
  padding: 0 .25rem;
}

@media all and (max-width: 768px) {
  li {
    font-size: 0.8rem;
    padding: 0.6rem;
  }

  li span {
    font-size: 2.3rem;
  }
}

.heart-container {
  width: 100%;
  height: 100%;
  position: relative;
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  align-items: center;
}

.heart {
  position: relative;
  font-size: 0;
  width: 138px;
}

[class*="heart-piece-"] {
  position: absolute;
  top: -5px;
  width: 10px;
  height: 10px;
  border-radius: 5px;
}

.heart-piece-4 {
  -webkit-animation: piece-4 3.2s infinite;
  animation: piece-4 3.2s infinite;
}

.heart-piece-3,
.heart-piece-5 {
  -webkit-animation: piece-3 3.2s infinite;
  animation: piece-3 3.2s infinite;
}

.heart-piece-2,
.heart-piece-6 {
  -webkit-animation: piece-2 3.2s infinite;
  animation: piece-2 3.2s infinite;
}

.heart-piece-1,
.heart-piece-7 {
  -webkit-animation: piece-1 3.2s infinite;
  animation: piece-1 3.2s infinite;
}

.heart-piece-0,
.heart-piece-8 {
  -webkit-animation: piece-0 3.2s infinite;
  animation: piece-0 3.2s infinite;
}

.heart-piece-0 {
  left: 0px;
  -webkit-animation-delay: 0s;
  animation-delay: 0s;
  background-color: #ec2d73;
}

.heart-piece-1 {
  left: 16px;
  -webkit-animation-delay: 0.15s;
  animation-delay: 0.15s;
  background-color: #eb5324;
}

.heart-piece-2 {
  left: 32px;
  -webkit-animation-delay: 0.3s;
  animation-delay: 0.3s;
  background-color: #fdc800;
}

.heart-piece-3 {
  left: 48px;
  -webkit-animation-delay: 0.45s;
  animation-delay: 0.45s;
  background-color: #47b264;
}

.heart-piece-4 {
  left: 64px;
  -webkit-animation-delay: 0.6s;
  animation-delay: 0.6s;
  background-color: #1470bd;
}

.heart-piece-5 {
  left: 80px;
  -webkit-animation-delay: 0.75s;
  animation-delay: 0.75s;
  background-color: #76469a;
}

.heart-piece-6 {
  left: 96px;
  -webkit-animation-delay: 0.9s;
  animation-delay: 0.9s;
  background-color: #ec2d73;
}

.heart-piece-7 {
  left: 112px;
  -webkit-animation-delay: 1.05s;
  animation-delay: 1.05s;
  background-color: #eb5324;
}

.heart-piece-8 {
  left: 128px;
  -webkit-animation-delay: 1.2s;
  animation-delay: 1.2s;
  background-color: #fdc800;
}

@-webkit-keyframes piece-4 {
  0%, 10%, 90%, 100% {
    height: 10px;
    top: -5px;
  }
  45%, 55% {
    height: 94px;
    top: -23px;
  }
}

@keyframes piece-4 {
  0%, 10%, 90%, 100% {
    height: 10px;
    top: -5px;
  }
  45%, 55% {
    height: 94px;
    top: -23px;
  }
}

@-webkit-keyframes piece-3 {
  0%, 10%, 90%, 100% {
    height: 10px;
    top: -5px;
  }
  45%, 55% {
    height: 90px;
    top: -31px;
  }
}

@keyframes piece-3 {
  0%, 10%, 90%, 100% {
    height: 10px;
    top: -5px;
  }
  45%, 55% {
    height: 90px;
    top: -31px;
  }
}

@-webkit-keyframes piece-2 {
  0%, 10%, 90%, 100% {
    height: 10px;
    top: -5px;
  }
  45%, 55% {
    height: 80px;
    top: -37px;
  }
}

@keyframes piece-2 {
  0%, 10%, 90%, 100% {
    height: 10px;
    top: -5px;
  }
  45%, 55% {
    height: 80px;
    top: -37px;
  }
}

@-webkit-keyframes piece-1 {
  0%, 10%, 90%, 100% {
    height: 10px;
    top: -5px;
  }
  45%, 55% {
    height: 60px;
    top: -31px;
  }
}

@keyframes piece-1 {
  0%, 10%, 90%, 100% {
    height: 10px;
    top: -5px;
  }
  45%, 55% {
    height: 60px;
    top: -31px;
  }
}

@-webkit-keyframes piece-0 {
  0%, 10%, 90%, 100% {
    height: 10px;
    top: -5px;
  }
  45%, 55% {
    height: 30px;
    top: -15px;
  }
}

@keyframes piece-0 {
  0%, 10%, 90%, 100% {
    height: 10px;
    top: -5px;
  }
  45%, 55% {
    height: 30px;
    top: -15px;
  }
}

</style>
