<template>
    <div>
        <h2>TODOS APP Vue </h2>
        <ol class="cd">
            <li :key="todo.id" v-for="todo in todos">
                <TodoItem v-bind:todo="todo"/>
            </li>
        </ol>
    </div>
</template>


<script>
import TodoItem from './Component/TodoItem.vue';
    export default {
        name:'todos',
        props:["todos"],
        components: {
            TodoItem
        }
        
    }
</script>

<style>
    
</style>