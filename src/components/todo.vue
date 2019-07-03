<!--
————————————————————————————————————————————————————————————————————————————————
—                                 TEMPLATE                                     —
————————————————————————————————————————————————————————————————————————————————
-->
<template>
  <div class="col-md-6 col-lg-12">
    <div class='card'>

      <div class="card-header" v-show="!isEditing">
        {{ todo.project }}
      </div>
      <div class="card-block" v-show="!isEditing">
        <div class='card-text'>
            {{ todo.title }}
        </div>
        <div class='extra content'>
            <span class='right floated edit icon' v-on:click="showForm">
            <i class='edit icon'></i>
          </span>
          <span class='right floated trash icon' v-on:click="deleteTodo(todo)">
            <i class='trash icon'></i>
          </span>
        </div>
      </div>

      <div class="card-header" v-show="isEditing">
          <label class="d-none">Project</label>
          <input class="form-control" type='text' v-model="todo.project" >
      </div>

      <div class="card-block" v-show="isEditing">
          <label class="d-none">Title</label>
          <input class="form-control" type='text' v-model="todo.title" >
      </div>


      <div class='btn btn-warning btn-block btn-noradiusTop' aria-label="Close" v-on:click="hideForm" v-show="isEditing">
          <span aria-hidden="true">Close &times;</span>
      </div>

      <div class='btn btn-success btn-noradiusTop' v-show="!isEditing &&todo.done" disabled>
          Completed
      </div>
      <div class='btn btn-secondary btn-noradiusTop' v-on:click="completeTodo(todo)" v-show="!isEditing && !todo.done">
          Pending
      </div>
    </div>
  </div>
</template>

<!--
————————————————————————————————————————————————————————————————————————————————
—                                 SCRIPTS                                      —
————————————————————————————————————————————————————————————————————————————————
-->
<script type="text/javascript">
  export default {
    props: ['todo'],
    data () {
      return {
        isEditing: false
      }
    },
    methods: {
      completeTodo (todo) {
        this.$emit('complete-todo', todo)
      },
      deleteTodo (todo) {
        this.$emit('delete-todo', todo)
      },
      showForm () {
        this.isEditing = true
      },
      hideForm () {
        this.isEditing = false
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
<style lang="scss" scoped>
.card{
  margin-bottom:1.5rem;
  position:relative;
  .card-block {
      -webkit-box-flex: 1;
      -webkit-flex: 1 1 auto;
      -ms-flex: 1 1 auto;
      flex: 1 1 auto;
      padding: 1.25rem;
  }

  .extra{
    position:absolute;
    top:0.8rem;
    right:0.5rem;
  }
}
</style>
