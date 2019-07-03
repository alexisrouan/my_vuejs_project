<!--
————————————————————————————————————————————————————————————————————————————————
— https://scotch.io/tutorials/build-a-to-do-app-with-vue-js-2                  —
————————————————————————————————————————————————————————————————————————————————
-->
<!--
————————————————————————————————————————————————————————————————————————————————
—                                 TEMPLATE                                     —
————————————————————————————————————————————————————————————————————————————————
-->
<template>
  <div>
    <div class='row'>
      <p class="tasks col-12">Completed Tasks: {{todos.filter(todo => {return todo.done === true}).length}}</p>
      <p class="tasks col-12">Pending Tasks: {{todos.filter(todo => {return todo.done === false}).length}}</p>
      <br/><br/>
    </div>
    <div class='row'>
        <todo
          v-on:delete-todo="deleteTodo"
          v-on:complete-todo="completeTodo"
          v-for="(todo, index)todo in todos" :todo.sync="todo" :key="todo.index">
        </todo>
    </div>
  </div>
</template>

<!--
————————————————————————————————————————————————————————————————————————————————
—                                 SCRIPTS                                      —
————————————————————————————————————————————————————————————————————————————————
-->
<script type = "text/javascript" >
import sweetalert from 'sweetalert'
import Todo from './todo'

export default {
  props: ['todos'],
  components: {
    Todo
  },
  methods: {
    deleteTodo (todo) {
      sweetalert({
      // VueSweetAlert({
        title: 'Are you sure?',
        text: 'This To-Do will be permanently deleted!',
        type: 'warning',
        showCancelButton: true,
        confirmButtonColor: '#DD6B55',
        confirmButtonText: 'Yes, delete it!',
        closeOnConfirm: false
      },
      () => {
        const todoIndex = this.todos.indexOf(todo)
        this.todos.splice(todoIndex, 1)
        sweetalert('Deleted!', 'Your To-Do has been deleted.', 'success')
        // VueSweetAlert('Deleted!', 'Your To-Do has been deleted.', 'success')
      })
    },
    completeTodo (todo) {
      const todoIndex = this.todos.indexOf(todo)
      this.todos[todoIndex].done = true
      sweetalert('Success!', 'To-Do completed!', 'success')
      // VueSweetAlert('Success!', 'To-Do completed!', 'success')
    }
  }
}
</script>

<!--
————————————————————————————————————————————————————————————————————————————————
—                                  STYLES                                      —
————————————————————————————————————————————————————————————————————————————————
-->
<style scoped>
  p.tasks {
    text-align: center;
  }
</style>
