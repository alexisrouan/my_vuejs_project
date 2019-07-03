<template>
  <div class='text-center'>
    <button class='btn btn-primary' v-on:click="openForm" v-show="!isCreating">
      Add
    </button>
    <div class='segment' v-show="isCreating">
      <div class='content'>

          <div class='form-group'>
            <label>Title</label>
            <input v-model="titleText" type='text' class="form-control">
          </div>
          <div class='form-group'>
            <label>Project</label>
            <input v-model="projectText" type='text' class="form-control">
          </div>
          <div class='row'>
            <div class="col-6">
              <button class='btn btn-primary btn-block col-' v-on:click="sendForm()">
                Create
              </button>
            </div>
            <div class="col-6">
              <button class='btn btn-warning btn-block' v-on:click="closeForm">
                Cancel
              </button>
            </div>
          </div>

      </div>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      titleText: '',
      projectText: '',
      isCreating: false
    }
  },
  methods: {
    openForm () {
      this.isCreating = true
    },
    closeForm () {
      this.isCreating = false
    },
    sendForm () {
      if (this.titleText.length > 0 && this.projectText.length > 0) {
        const title = this.titleText
        const project = this.projectText
        this.$emit('create-todo', {
          title,
          project,
          done: false
        })
        this.titleText = ''
        this.projectText = ''
        this.isCreating = false
      }
    }
  }
}
</script>
