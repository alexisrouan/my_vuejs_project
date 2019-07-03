<!--
————————————————————————————————————————————————————————————————————————————————
—                                 TEMPLATE                                     —
————————————————————————————————————————————————————————————————————————————————
-->
<template>
  <div id="app">
    <img src="./assets/logo.png" class="vue-logo">
    <div class="container">
      <!-- row -->
      <div class="row">
        <div class="col-sm-12 col-md-6 col-lg-4">
          <hello class="my-componant"></hello>
          <list-renderer class="my-componant"></list-renderer>
        </div>
        <div class="col-sm-12 col-md-6 col-lg-4">
          <server-count class="my-componant"></server-count>
          <button-click class="my-componant"></button-click>
          <listen-event class="my-componant"></listen-event>
          <ajax-call class="my-componant"></ajax-call>
        </div>
        <div class="col-sm-12 col-md-12 col-lg-4">
          <TodoListMain class="my-componant"></TodoListMain>
        </div>
        <div class="col-12">
          <Communic class="my-componant"></Communic>
        </div>
      </div>
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
import Hello from './components/Hello'
import ButtonClick from './components/button-click'
import TodoListMain from './components/todo-main'
import ServerCount from './components/server-count'
import ListRenderer from './components/list-renderer'
import ListenEvent from './components/listen-event'
import AjaxCall from './components/ajax-call'
import Communic from './components/communicate-main'

export default {
  name: 'app',
  components: {
    Hello,
    ButtonClick,
    TodoListMain,
    ServerCount,
    ListRenderer,
    ListenEvent,
    AjaxCall,
    Communic
  }

}
</script>

<!--
————————————————————————————————————————————————————————————————————————————————
—                                 STYLES                                       —
————————————————————————————————————————————————————————————————————————————————
-->
<style lang="scss" src="./assets/stylesheets/styles.scss"></style>
