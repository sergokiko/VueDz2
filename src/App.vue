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


    />
    <button  v-on:click="remove"> Remove</button>
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
      list: [
          {todo:'Meting with client', completed: false},
          {todo:'Go to gym',completed: false},
          {todo:'Visit Mum',completed: false},
          {todo:'bla bla', completed: false}
        ],
      toDo: ''
    }
  },
  methods:{
    addItem(item){
        this.list.push(item)
    },
    remove(){
      this.list = this.list.filter(el => !el.completed)

    }
  }

}
</script>

<style>

</style>
