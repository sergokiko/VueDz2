<template>
  <div>
    <h1>{{message}}</h1>
    <AddTodo
        v-if="list.length <10"
    :list="list"
    @addToDo="addItem"
    />
    <TodoList
        :list ="list"
        @remove="removeItem"
    />
  </div>
</template>

<script>
import AddTodo from "@/components/AddTodo";
import TodoList from "@/components/TodoList";
export default {
  name: 'App',
  components:{

    AddTodo,
    TodoList
  },
  data(){
    return{
      message: 'ToDo',
      list: ['Meting with client', 'Go to gym', 'Visit Mum' ],
      toDo: ''
    }
  },
  methods:{
    removeItem(index){
      this.list.splice(index,1)
    },
    addItem(item){
        this.list.push(item)
    }
  }
}
</script>

<style>

</style>
