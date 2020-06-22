<template>
<div>
    <div v-bind:key="t.id" v-for="t in todos">
<TodoItem  v-bind:t="t" v-on:del_todo="$emit('del_todo',t.id)"/>
    </div>

    </div>
</template>

<script>
import TodoItem from './TodoItem';
export default {
   
    name:"Todos",
     components:{
        TodoItem
    },
    props:["todos"]
}
</script>

<style scoped>

</style>