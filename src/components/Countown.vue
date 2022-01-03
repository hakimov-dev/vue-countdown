// Created by Hakimov-dev
<template>
    <div class="coming-soon-area">
        <div class="container  md:w-2/3 mx-auto">
            <div class="coming-soon-content">
                <div class="d-table">
                    <div class="d-table-cell">
                       <h1 class="title text-3xl font-bold text-center">Countdown in Vue 3 cli</h1>
                        <div class="timer items-center justify-between flex ">
                            <div
                                id="days"
                                class="time items-center flex-col flex justify-center"
                            >
                                <h3>{{days}}</h3>
                                <p>Days</p>
                            </div>
                            <div
                                id="hours"
                                class="time items-center flex-col flex justify-center"
                            >
                                <h3>{{hours}}</h3>
                                <p>Hours</p>
                            </div>
                            <div
                                id="minutes"
                                class="time items-center flex-col flex justify-center"
                            >
                                <h3>{{minutes}}</h3>
                                <p>Minutes</p>
                            </div>
                            <div
                                id="seconds"
                                class="time items-center flex-col flex justify-center md:flex hidden"
                            >
                                <h3>{{seconds}}</h3>
                                <p>Seconds</p>
                            </div>
                        </div>
                    </div>
                </div>
                <h4 class="text-center text-3xl created">Created by <a href="http://hakimov.netlify.com" target="_blank" rel="noopener noreferrer">&copy;Hakimov-dev</a></h4>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'ComingSoonPage',
    data() {
        return {
            days: '',
            hours: '',
            minutes: '',
            seconds: ''
        }
    },
    created() {
        setInterval(() => {
            this.commingSoonTime();
        });
    },
    methods: {
        commingSoonTime() {
            let endTime = new Date("December 1, 2028 00:00:00 PDT");            
            let endTimeParse = (Date.parse(endTime)) / 1000;
            let now = new Date();
            let nowParse = (Date.parse(now) / 1000);
            let timeLeft = endTimeParse - nowParse;
            let days = Math.floor(timeLeft / 86400);
            let hours = Math.floor((timeLeft - (days * 86400)) / 3600);
            let minutes = Math.floor((timeLeft - (days * 86400) - (hours * 3600 )) / 60);
            let seconds = Math.floor((timeLeft - (days * 86400) - (hours * 3600) - (minutes * 60)));
            if (hours < "10") { hours = "0" + hours; }
            if (minutes < "10") { minutes = "0" + minutes; }
            if (seconds < "10") { seconds = "0" + seconds; }
            this.days = days;
            this.hours = hours;
            this.minutes = minutes;
            this.seconds = seconds;
        }
        // Created by Hakimov-dev
    }
}
</script>


<style scoped>



    :root{
  --clr-bg1:#252525FF;
  --clr-bg2:#3B3B3BFF; 
  --clr-main:#0fff;
  --clr-main2:#00C4F0FF;
  --clr-text:#E4E4E4FF;
}

.created{
  position: absolute;
  bottom: 10%;
  left: 40%;
}

.created a{
  color: var(--clr-main2);
  font-weight: 600;
}

.time{
  background: var(--clr-bg1);
  padding: 60px 80px;
}

.container{
  color: var(--clr-text);
  animation-name: content;
  animation-timing-function: linear;
  animation-duration: 1s;
}

.timer{
      animation-name: content;
  animation-timing-function: linear;
  animation-duration: 2s;
  /* Created by Hakimov-dev */
}

@keyframes content {
  0%{
    opacity: 0; transform: translateY(80%);
  }
  25%{
    opacity: .2; transform: translateY(40%);
  }
  50%{
    opacity: .5; transform: translateY(20%);
  }
  75%{
    opacity: .7; transform: translateY(10%);
  }
  100%{
    opacity: 1; transform: translateY(0%);
  }
}


 .d-table {
  width: 100%;
  height: 100%;
}
.d-table-cell {
  vertical-align: middle;
}

.title{
  color: var(--clr-text);
  margin-bottom: 80px !important;
}

.coming-soon-content {
  height: 100vh;
  text-align: center;
  padding-left: 30px;
  padding-right: 30px;
}
.coming-soon-content .logo {
  display: inline-block;
}
.coming-soon-content h2 {
  font-size: 70px;
  color: var(--clr-main2);
  margin-top: 30px;
  margin-bottom: 0;
  /*  Created by Hakimov-dev */
}
.coming-soon-content .timer {
  margin-top: 35px;
}
.coming-soon-content .timer .time {
 text-align: center;
  width: 120px;
  height: 110px;
  border-radius: 5px;
  background-color:var(--clr-bg2) ;
  margin-left: 10px;
  margin-right: 10px;
}
.coming-soon-content .timer .time h3 {
    color: var(--clr-main2);
  font-size: 50px;
  font-weight: 700;
  font-style: italic;
}
.coming-soon-content .timer .time p {
  display: block;
  margin-top: -2px;
  color: var(--clr-text);
  font-size: 20px;
  font-weight: 500;
}
.coming-soon-content .timer .time:first-child {
  margin-left: 0;
}
.coming-soon-content .timer .time:last-child {
  margin-right: 0;
}
</style>