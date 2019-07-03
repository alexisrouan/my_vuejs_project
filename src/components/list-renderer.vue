<!--
————————————————————————————————————————————————————————————————————————————————
—                                 TEMPLATE                                     —
————————————————————————————————————————————————————————————————————————————————
-->
<template>
  <div>
    <h1>{{ title }}</h1>
    <h2>Exemple 1</h2>
    <ul id="example-1" class="list-group">
      <li v-for="item in items" class="list-group-item">
        {{ item.message }}
      </li>
    </ul>
    <h2>Exemple 2</h2>
    <ul id="example-2" class="list-group">
      <li v-for="(item, index) in items" class="list-group-item">
        {{ parentMessage }} - {{ index }} - {{ item.message }}
      </li>
    </ul>
    <h2>V-for</h2>
    <ul class="list-group">
      <template v-for="item in items">
        <li class="list-group-item">{{ item.message }}</li>
      </template>
    </ul>
    <h2>Repeat object</h2>
    <ul id="repeat-object" class="list-group">
      <li v-for="(value, key) in object" class="list-group-item">
        {{ key }} : {{ value }}
      </li>
    </ul>
  </div>
</template>

<!--
————————————————————————————————————————————————————————————————————————————————
—                                 SCRIPTS                                      —
————————————————————————————————————————————————————————————————————————————————
-->
<script>
export default {
  name: 'list-renderer',
  data () {
    return {
      title: 'List renderer',
      parentMessage: 'Parent',
      items: [
        { message: 'Foo' },
        { message: 'Bar' }
      ],
      object: {
        firstName: 'John',
        lastName: 'Doe',
        age: 30
      }
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
</style>
