<template>
  <div>
    <ul>
      <TodoItem
          v-for="(item,i) in list"
          :key="i"
          :todo="item"
          :index="i"
          @remove="removeTodo"
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
  methods:{
    removeTodo(index){
  this.$emit('remove' , index)
    }
  }


}
</script>