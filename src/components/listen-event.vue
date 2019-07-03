<!--
————————————————————————————————————————————————————————————————————————————————
—                                 TEMPLATE                                     —
————————————————————————————————————————————————————————————————————————————————
-->
<template>
  <div>
    <h1>{{ title }}</h1>
    <button
      class="btn btn-success"
      v-on:click="counter += 1">
          Click me!
    </button>
    <br/><br/>
    <p>The button above has been clicked {{ counter }} times.</p>
  </div>
</template>

<!--
————————————————————————————————————————————————————————————————————————————————
—                                 SCRIPTS                                      —
————————————————————————————————————————————————————————————————————————————————
-->
<script>
export default {
  name: 'listen-event',
  data () {
    return {
      title: 'Listen Event',
      counter: 0
    }
  },
  created () {
    // console.log('this created')
  }
}
</script>
<!--
————————————————————————————————————————————————————————————————————————————————
—                                  STYLES                                      —
————————————————————————————————————————————————————————————————————————————————
-->
<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
</style>
