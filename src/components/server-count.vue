<template>
  <div class="my-componant">
    <h1>{{ title }}</h1>
    You have been here for {{ counter }} seconds.
  </div>
</template>

<script>
  export default {
    name: 'server-count',
    data () {
      return {
        title: 'Counter',
        counter: 0
      }
    },
    created () {
      console.log('server-count created')
      var vm = this
      setInterval(function () {
        vm.counter += 1
      }, 1000)
    }
  }
</script>
<style>
</style>
