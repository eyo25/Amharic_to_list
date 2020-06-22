<template>
    <div>
<form  @submit.prevent="addtodo">

<input type="text"  v-model="title" name="title" placeholder="ያቀድከውን ስራ አስገባ">
<input type="submit"  value="አስቀምጥ" class="btn">
</form>


    </div>
</template>

<script>
//import uuid from 'uuid';
export default {
   name:"Addtodos",
   data(){
       return{
           title:''
       }
   },
   methods:{
       addtodo(){
           //e.preventDefault();
           const newTodo={
               
               title:this.title,
               completed:false
           }
           this.$emit('add-todo',newTodo);
           this.title='';

       }
   } 
}
</script>

<style scoped>
form{
    display: flex;
}
input[type="text"]{
    flex: 10;
    padding: 5px;
}
input[type="submit"]{
    flex: 2;
}
</style>