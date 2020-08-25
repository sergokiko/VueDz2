<template>
  <div>
    <input type="text" v-model="newTodo">
    <button @click="addTodo">Add</button>
  </div>
</template>
<script>

export default {
  name: 'AddTodo',
  props:{
    list:{
      type: Array,
      required: true
    }
  },
  data(){
    return{
      newTodo:''
    }
  },
  methods:{
    addTodo(){
        let  obj = {
          todo: this.newTodo,
          completed: true
        }
        this.$emit('addToDo', obj)
        this.newTodo = ''

    }
  }
}
</script>