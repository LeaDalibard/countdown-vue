<template>
  <div>
<Counter/>
  </div>
</template>

<script>

import Counter from "@/components/Counter";

export default {
  name: 'Home',
  components: {Counter},
  props: {
    msg: String
  }
}
</script>

<style scoped>

</style>