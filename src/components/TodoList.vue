<template>
  <div>
    <ul>
      <TodoItem
          v-for="(item,i) in list"
          :key="i"
          :todo="item"
          :id = "i"
      />
    </ul>

  </div>

</template>
<script>
import TodoItem from "@/components/TodoItem";

export default {
  name:'TodoList',
  components:{
    TodoItem
  },
  props:{
    list:{
      type: Array,
      required:true
    }
  },



}
</script>