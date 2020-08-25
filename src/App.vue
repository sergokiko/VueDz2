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
    <button v-on:click="remove"> Remove</button>
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
          {todo:'Meting with client', completed: true},
          {todo:'Go to gym',completed: true},
          {todo:'Visit Mum',completed: true}
        ],
      toDo: ''
    }
  },
  methods:{
    addItem(item){
        this.list.push(item)
    },
    remove(){
      console.log(this.list);
      this.list = this.list.filter(el => el.completed)
      console.log(this.list);
    }
  }

}
</script>

<style>

</style>
