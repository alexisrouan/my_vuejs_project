<!--
https://github.com/mzabriskie/axios

————————————————————————————————————————————————————————————————————————————————
—                                 TEMPLATE                                     —
————————————————————————————————————————————————————————————————————————————————
-->
<template>
  <div>
    <h1>{{ title }}</h1>
    <div class="row">
      <div class="col-6">
        <button v-on:click="tamporize('http://localhost:8080/static/ajax/test-ajax.json')" class="btn btn-success btn-block">Get Ajax</button>
      </div>
      <div class="col-6">
        <button v-on:click="tamporize('http://localhost:8080/static/ajax/test-ajax0.json')" class="btn btn-danger btn-block">Call wrong file</button>
      </div>
    </div>

      <div class="segment">
        <div class="ui inverted dimmer" v-bind:class="{ active: isActive }">
          <div class="ui text loader">waiting 2000ms</div>
        </div>
        <p>{{ ajaxResponse }}</p>
      </div>
  </div>
</template>

<!--
————————————————————————————————————————————————————————————————————————————————
—                                 SCRIPTS                                      —
————————————————————————————————————————————————————————————————————————————————
-->
<script>
import sweetalert from 'sweetalert'
import axios from 'axios'

// export
export default {
  name: 'ajax-call',
  data () {
    return {
      title: 'Ajax Call with Axios',
      ajaxResponse: '{{ ajax response }}',
      isActive: false
    }
  },
  created () {
    console.log('this created')
  },
  methods: {
    // TAMPORIZE
    tamporize: function (file) {
      this.isActive = true
      this.ajaxResponse = '{{ ajax response }}'
      setTimeout(this.axiosGetMethod, 2000, file)
    },
    // METHOD 1 : GET
    axiosGetMethod: function (file) {
      axios.get(file)
      .then((response) => {
        console.log(response.data)
        this.ajaxResponse = response.data
        this.isActive = false
      })
      .catch((error) => {
        console.log(error)
        this.ajaxResponse = 'Not found!'
        this.isActive = false
        popupError()
      })
    },
    // METHOD 2 : POST
    axiosPostMethod: function () {}
  }
}

// Function Popup
var popupError = function () {
  sweetalert({
    title: 'File not found',
    text: 'The file was not found !',
    type: 'warning',
    showCancelButton: false,
    confirmButtonColor: '#DD6B55',
    confirmButtonText: 'Good job!',
    closeOnConfirm: false
  },
  () => {
    sweetalert.close()
  })
}
</script>

<!--
————————————————————————————————————————————————————————————————————————————————
—                                  STYLES                                      —
————————————————————————————————————————————————————————————————————————————————
-->
<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
  .text{
    font-family: monospace;
  }
</style>
