<!--
————————————————————————————————————————————————————————————————————————————————
—                                 TEMPLATE                                     —
————————————————————————————————————————————————————————————————————————————————
-->
<template>
  <div>
    <h1>{{ title }}</h1>
    <div class="row">
      <div class="col-sm-12 col-md-6 col-lg-4">
        <div class="">
          <h1>Parent</h1>
          <p>Message (<strong>child1</strong>) : {{ msgChild1 }}</p>
          <p>Message (<strong>child2</strong>) : {{ msgChild2 }}</p>
        </div>
      </div>
      <div class="col-sm-12 col-md-6 col-lg-4">
        <CommunicateChild1 class="my-componant"></CommunicateChild1>
      </div>
      <div class="col-sm-12 col-md-6 col-lg-4">
        <CommunicateChild1 class="my-componant"></CommunicateChild1>
      </div>
    </div>
  </div>
</template>

<!--
————————————————————————————————————————————————————————————————————————————————
—                                 SCRIPTS                                      —
————————————————————————————————————————————————————————————————————————————————
-->
<script>
import CommunicateChild1 from '../components/communicate-child1'
import Vue from 'vue'
var Bus = new Vue()
// const Bus = new Vue()
console.log('Bus=' + Bus)

export default {
  name: 'communicate',
  data () {
    return {
      title: 'Components communication',
      msgChild1: '',
      msgChild2: ''
    }
  },
  components: {
    CommunicateChild1
  },
  created () {
    // console.log('this created')
    // Listen Event ------------------
    Bus.$on('updateMsgChild1', () => {
      console.log('parent handling the event')
      this.msgChild1 = 'ok'
    })
  },
  methods: { }
}
</script>

<!--
————————————————————————————————————————————————————————————————————————————————
—                                  STYLES                                      —
————————————————————————————————————————————————————————————————————————————————
-->
<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped></style>
