<!--
————————————————————————————————————————————————————————————————————————————————
—                                 TEMPLATE                                     —
————————————————————————————————————————————————————————————————————————————————
-->
<template>
  <div>
    <h1>{{ msg }}</h1>
    <button v-on:click="sayHello" class="btn btn-primary">Click here plz!</button>
  </div>
</template>

<!--
————————————————————————————————————————————————————————————————————————————————
—                                 SCRIPTS                                      —
————————————————————————————————————————————————————————————————————————————————
-->
<script>
import sweetalert from 'sweetalert'

export default {
  name: 'button-click',
  data () {
    return {
      msg: 'Componant button-click',
      name: 'this.name'
    }
  },
  methods: {
    sayHello: function () {
      // alert('Hey there, ' + this.name)
      sweetalert('Good job!', 'You clicked the button!', 'success')
    }
  }
}
</script>

<!--
————————————————————————————————————————————————————————————————————————————————
—                                  STYLES                                      —
————————————————————————————————————————————————————————————————————————————————
-->
<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
