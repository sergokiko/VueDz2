<template>

    <li>
      <input type="checkbox"  @change="todo.completed = !todo.completed">
        {{todo.todo}}
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
    index:{
      type: Number,
      required: true
    }
  },
  methods:{
    dosomesithg(){
      console.log(this.todo);
    }
  }
}
</script>
<style scoped>

</style>