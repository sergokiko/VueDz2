<template>

    <li>


      <label :for="id"><input  type="checkbox" :id="id"   @change="todo.completed = !todo.completed">{{todo.todo}}</label>

    </li>

</template>
<script>
export default {
  name: 'TodoItem',
  props:{
    todo:{
      type: Object,
      required:true,
    },
    id:{
      type: Number,
      required: true
    }

  },

}
</script>
<style scoped>

</style>