<template>
  <div>
    <h1>Counter</h1>
    <p>Days : {{  displayDays }}</p>
    <p>Hours : {{  displayHours }}</p>
    <p>Minutes : {{ displayMinutes }}</p>
    <p>Seconds : {{ displaySeconds }}</p>

  </div>
</template>

<script>
export default {
  name: 'Counter',
  data: function () {
    return {
      displayDays: 0,
      displayHours: 0,
      displayMinutes: 0,
      displaySeconds: 0,
    }
  },
  computed: {
    _seconds: () => 1000,
    _minutes() {
      return this._seconds * 60
    },
    _hours() {
      return this._minutes * 60
    },
    _days() {
      return this._hours * 24
    },
  },
  mounted () {
    this.showRemaining();
  },
  methods: {
    showRemaining() {
      const time = setInterval(function () {

        const now= new Date();
        const end= new Date(2021, 1, 8, 17,0);

        //var currentDate = new Date();
        //var endDate = 1609779600000;
        //var diff = Math.abs(endDate - currentDate);

        const distance=end-now;

        if(distance<0){
          clearInterval(time);
        }

        const days = Math.floor(distance / this._days);
        const hours = Math.floor((distance % this._days) / this._hours);
        const minutes = Math.floor((distance % this._hours) / this._minutes);
        const seconds = Math.floor((distance % this._minutes) / this._seconds);

        this.displayDays =days;
        this.displayHours = hours;
        this.displayMinutes = minutes;
        this.displaySeconds = seconds;

        //days
        //this.days = Math.floor(diff / this.daysInMs);
        //console.log(this.daysInMs);
        //diff -= this.days * this.daysInMs;


        //hours
        //this.hours = Math.floor(diff / this.hoursInMs) % 24;
        //diff -= this.hours * this.hoursInMs

        //minutes
        //this.minutes = Math.floor(diff / this.minutesInMs) % 60;
        //console.log(secondsInMs);
        //diff -= this.minutes * this.minutesInMs;

        //seconds
        //this.seconds = Math.floor(diff / this.secondsInMs) % 60;
      }, 1000);

    }

  }

}
</script>

<style scoped>

</style>