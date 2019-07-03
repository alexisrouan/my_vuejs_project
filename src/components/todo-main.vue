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
      <h1>{{ title }}</h1>
      <todo-list v-bind:todos="todos"></todo-list>
      <create-todo v-on:create-todo="createTodo"></create-todo>
    </div>
</template>

<!--
————————————————————————————————————————————————————————————————————————————————
—                                 SCRIPTS                                      —
————————————————————————————————————————————————————————————————————————————————
-->
<script>
import TodoList from '../components/todo-list'
import CreateTodo from '../components/todo-create'
import sweetalert from 'sweetalert'

export default {
  name: 'todolistmain',
  // COMPONENTS
  components: {
    TodoList,
    CreateTodo
  },
  // data function avails data to the template
  data () {
    return {
      title: 'To Do List',
      todos: [{
        id: 1,
        title: 'Todo A',
        project: 'Project A',
        done: false
      }, {
        id: 2,
        title: 'Todo B',
        project: 'Project B',
        done: true
      }, {
        id: 3,
        title: 'Todo C',
        project: 'Project C',
        done: false
      }, {
        id: 4,
        title: 'Todo D',
        project: 'Project D',
        done: false
      }]
    }
  },
  methods: {
    createTodo (newTodo) {
      this.todos.push(newTodo)
      // VueSweetAlert('Success!', 'To-Do created!', 'success')
      sweetalert('Success!', 'To-Do created!', 'success')
    }
  }
}
</script>

<!--
————————————————————————————————————————————————————————————————————————————————
—                                  STYLES                                      —
————————————————————————————————————————————————————————————————————————————————
-->
<style lang="scss" scoped>
</style>
