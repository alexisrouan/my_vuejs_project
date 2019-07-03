<!--
————————————————————————————————————————————————————————————————————————————————
—                                 TEMPLATE                                     —
————————————————————————————————————————————————————————————————————————————————
-->
<template>
  <div>
    <h1>{{ title }}</h1>
    <div class="form-group">
      <input v-model="msgChild1" placeholder="modifiez-moi" v-on:keyup="keyUpEvent" >
    </div>
    <p>Message (<strong>child1</strong>) : {{ msgChild1 }}</p>
    <p>Message (<strong>child2</strong>) : {{ msgChild2 }}</p>
  </div>
</template>

<!--
————————————————————————————————————————————————————————————————————————————————
—                                 SCRIPTS                                      —
————————————————————————————————————————————————————————————————————————————————
-->
<script>
import Vue from 'vue'
var Bus = new Vue()

export default {
  name: 'communicate-child1',
  data () {
    return {
      title: 'Child 1',
      msgChild1: '',
      msgChild2: ''
    }
  },
  created () {
    // console.log('this created')
    /* Bus.$on('updateMsgChild1', () => {
      console.log('Child1 handling the event')
    }) */
  },
  methods: {
    keyUpEvent: function () {
      console.log('child1: keyUpEvent : msg1=' + this.msgChild1)
      Bus.$emit('updateMsgChild1', this.msgChild1)
      // this.$emit('updateMsgChild1')
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
<style lang="scss" scoped></style>
