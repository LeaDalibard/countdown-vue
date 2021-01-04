<template>
  <div>
    <h1>Counter</h1>
    <p>Days : {{ days }}</p>
    <p>Hours : {{ hours }}</p>
    <p>Minutes :  {{ minutes }}</p>
    <p>Seconds : {{ seconds }}</p>
{{this.hoursInMs}}
    {{this.daysInMs}}
  </div>
</template>

<script>
export default {
  name: 'Counter',
  data: function () {
    return {
      days: 0,
      hours: 0,
      minutes: 0,
      seconds: 0,
      endDate:1609779600000,
    }
  },
  computed: {
    secondsInMs: function () {
      return 1000
    },
    minutesInMs: function () {
      return 60 * 1000
    },
    hoursInMs: function () {
      return 60 * 60 * 1000
    },
    daysInMs: function () {
      return 24 * 60 * 60 * 1000
    },
  },
  methods: {
    showRemaining() {
      var currentDate=new Date();
      var diff= Math.abs(this.endDate-currentDate);

      //days
      this.days= Math.floor(diff/this.daysInMs);
      diff-=this.days*this.daysInMs;

      //hours
      this.hours=Math.floor(diff / this.hoursInMs)%24 ;
      diff-=this.hours*this.hoursInMs

      //minutes
      this.minutes=Math.floor(diff/this.minutesInMs)%60;
      diff-=this.minutes*this.minutesInMs;

      //seconds
      this.seconds=Math.floor(diff/this.secondsInMs)%60;
    }

  }

}
</script>

<style scoped>

</style>