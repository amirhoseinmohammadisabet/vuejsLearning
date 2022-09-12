<script>
  export default {
  name: "DigitalClock",
  data() {
    return {
      hours: 0,
      minutes: 0,
      seconds: 0
    }
  },
  mounted() {
    setInterval(() => this.setTime(), 1000)
  },
  methods: {
    setTime() {
      const date = new Date();
      let hours = date.getHours();
      let minutes = date.getMinutes();
      let seconds = date.getSeconds();
      hours = hours <= 9 ? `${hours}`.padStart(2, 0) : hours;
      minutes = minutes <= 9 ? `${minutes}`.padStart(2, 0) : minutes;
      seconds = seconds <= 9 ? `${seconds}`.padStart(2, 0) : seconds;
      this.hours = hours;
      this.minutes = minutes;
      this.seconds = seconds;
    }
  }
}
</script>
  
  <template>
    <h1>{{ message }}</h1>
  <body>
  
        <div class="phoneframe">
            <div class="clock">
                <div class="inner-clock-face">
                    <div class="first_hand"></div>
                    <div class="second_hand"></div>
                    <div class="third_hand"></div>
                </div>
            </div>
            <div class="digital_clock">
              <div class="config">
  <div class="container">
    <div class="LCD">
      <div class="hours">{{ hours }}</div>
      <div class="divider">:</div>
      <div class="minutes">{{ minutes }}</div>
      <div class="divider">:</div>
      <div class="seconds">{{ seconds }}</div>
    </div>
  </div>
            </div>
            <div class="underline"></div>
            <br>
            <div class="quote">
                Better three hours too soon than a minute too late.
            </div>
        </div>
    </div>
</body>

</template>

<style>
  html {
  display: flex;
  background: lightgray;
  text-align: center;
  font-size: 9px;
}
  body {
  font-family: roboto;
  margin-top: 0px;
  font-size: 2rem;
  display: flex;
  flex: 1;
  min-height: 100vh;
  align-items: center;
  justify-content: center;
  background-color: lightgray;
}


body .phoneframe {
  width: 240px;
  height: 500px;
  border-radius: 10px;
  padding: 8px 12px;
  background-color: rgba(173, 173, 173, 0.38);
  box-shadow: -5px 0px 10px rgb(175, 175, 175) inset;
}

.clock {
  background-color: rgb(224, 224, 224);
  width: 13rem;
  height: 13rem;
  position: relative;
  padding: 2rem;
  border: 7px solid rgb(240, 238, 238);
  box-shadow: -4px -4px 10px lightgray,
    4px 4px 10px lightgray;
  border-radius: 50%;
  margin: 80px auto;
}

.inner-clock-face {
  position: absolute;
  top: 10%;
  left: 10%;
  width: 80%;
  height: 80%;
  border-radius: 100%;
  z-index: 1;
}

.inner-clock-face::before {
  content: '';
  position: absolute;
  top: 50%;
  left: 50%;
  width: 6px;
  height: 6px;
  border-radius: 18px;
  margin-left: -3px;
  margin-top: -2px;
  background: rgb(156, 8, 8);
  z-index: 11;
}

.first_hand {
  width: 50%;
  right: 50%;
  height: 6px;
  background: rgb(34, 34, 34);
  position: absolute;
  top: 50%;
  border-radius: 6px;
  transform-origin: 100%;
  transform: rotate(250deg);
  height: 3px;
  width: 25%;
  z-index: 1;
}

.second_hand {
  width: 50%;
  right: 50%;
  height: 6px;
  background: rgb(34, 34, 34);
  position: absolute;
  top: 50%;
  border-radius: 6px;
  transform-origin: 100%;
  transform: rotate(135deg);
  height: 3px;
  z-index: 2;
  width: 40%;
}

.third_hand {
  width: 50%;
  right: 50%;
  height: 6px;
  background: #61afff;
  position: absolute;
  top: 50%;
  border-radius: 6px;
  transform-origin: 100%;
  transform: rotate(35deg);
  background: rgb(156, 8, 8);
  z-index: 3;

  width: 45%;
  height: 2px;
}

.digital_clock {
  position: relative;
  font-family: roboto;
  font-size: 40px;
}

.underline {
  position: relative;
  margin-left: 50px;
  background: #61afff;
  border-radius: 6px;
  width: 15%;
  height: 3px;
}

.quote {
  font-family: roboto;
  font-size: 1rem;
  opacity: 0.7;
}

.config{
  width:200px;
  position: relative;
}

.LCD {

  display: flex;
  align-items:center;
  margin-left:auto;
  margin-left: 50px;
}
.LCD > div {
  padding:5px;
  align-items:center;
  font-family: "alarm clock";
  font-size: x-large;
}
</style>