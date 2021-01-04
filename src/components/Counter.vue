<template>
  <div>
    <h1>Counter</h1>
    {{days}}
    {{hours}}
    {{minutes}}
    {{seconds}}
  </div>
</template>

<script>
export default {
  name: 'Counter',
  data: function() {
    return {
      days: 0,
      hours:0,
      minutes:0,
      seconds:0
    }
  },
}
</script>

<style scoped>

</style>