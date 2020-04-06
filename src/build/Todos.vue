<template>
    <div>
     <h2>TODOS APP    </h2>
        <input   type="text"  v-model="newItem"  v-on:keyup.enter="addItem">
        <button @click="addItem">Click To add Item</button>
        <ol>
            <li :key="item" v-for="item in items">
                {{ item }}
            </li>
        </ol>
    </div>
</template>

<script>
    export default {
        newItem:'',
        data() {
            return {
                items: [],
            }
        },
        
        methods: {
            addItem() {
               this.items.push(this.newItem)
               this.newItem = ''
            }
        }
    }
</script>

<style>
    .red {
        border:2px solid red;
    }
    
    .green {
        border:2px solid green;
    }
</style>