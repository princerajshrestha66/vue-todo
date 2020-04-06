<template>
    <div class="todo-item" v-bind:class="{'is-completed':todo.completed}">
       <p>
             <input type="checkbox" v-on:change="markComplete">
            {{todo.title}}
            <button v-on:click="del-todo" class="del">X</button>
       </p>
    </div>
</template>


<script>
export default {
    name:'TodoItem',
    props:["todo"],
    methods: {
        markComplete() {
            this.todo.completed = !this.todo.completed;
        }
    }
}
</script>


<style>
    .todo-item {
        background:#f4f4f4;
        padding:10px;
        border-bottom:1px solid #ccc; 
    }
    
    .is-completed {
        text-decoration:line-through; 
    }
    
    .del {
        background:#900;
        color:#fff;
        border:none;
        padding:5px 9px;
        border-radius: 50%;
        cursor: pointer;
        float:right;
    }
</style>