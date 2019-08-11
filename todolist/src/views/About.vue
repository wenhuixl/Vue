<template>
  <div class="about">
    <h1>This is an about page</h1>
    <input v-model="inputValue">
    <button @click="submit">提交</button>
    <ul>
      <todo-item v-for="(item, index) in list" :content="item" :index="index" @mydelete="handledelete"></todo-item>
    </ul>
  </div>
</template>

<script>
  import TodoItem from '../components/TodoItem'

  export default {
    components: {
      'todo-item': TodoItem
    },
    data () {
      return {
        inputValue: '',
        list: []
      }
    },
    methods: {
      submit () {
        this.list.push(this.inputValue)
        this.inputValue = ''
      },
      handledelete (index) {
        this.list.splice(index, 1)
      }
    }
  }
</script>
