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
      if(this.newTodo.trim()){
        this.$emit('addToDo', this.newTodo)
        this.newTodo = ''
      }
    }
  }
}
</script>