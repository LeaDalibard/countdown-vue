<template>
  <div>
    <h1>Counter</h1>
    {{ days }}
    {{ hours }}
    {{ minutes }}
    {{ seconds }}
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
      seconds: 0
    }
  },
  computed: {
    secondsInMs: function () {
      return 1000
    },
    minutesInMs: function () {
      return 60*1000
    },
    hoursInMs: function () {
      return 60*60*1000
    },
    daysInMs: function () {
      return 36*60*60*1000
    },
  }
}
</script>

<style scoped>

</style>