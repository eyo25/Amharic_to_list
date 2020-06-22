<template>
  <div id="app">
    <Header/>
    <Addtodos  v-on:add-todo="addtodo"/>
    <Todos v-bind:todos="todos" v-on:del_todo="deleteTodo" />
  </div>
</template>

<script>
import Todos from './components/Todos';
import Header from'./components/Layout/Header'
import Addtodos from './components/Addtodos'

export default {
  name: 'App',
  components: {
    Todos,
    Header,
    Addtodos
  },
  data(){
    return{
todos:[
  {
id: 1,
title: "ስራ አንድ",
completed:false

  },
   {
id: 2,
title: "ስራ ሁለት",
completed:true

  },
   {
id: 3,
title: "ስራ ሶስት",
completed:false

  }
]
   } 
    

  },

  methods: {


     deleteTodo(id){
this.todos=this.todos.filter(t=>t.id!==id);
     },
     addtodo(newTodo){

       this.todos=[...this.todos,newTodo];
     }
   } 
}
</script>

<style>
*{
box-sizing: border-box;
margin: 0;
padding: 0;
}


body{

  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.4;
}
.btn{
display: inline-block;
border: none;
background: #666;
color: #fff;
padding: 7px 20px;
cursor: pointer;
}
.btn:hover{
  background: orchid;
}
</style>
