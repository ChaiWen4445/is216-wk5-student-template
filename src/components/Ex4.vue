<script setup>
import { ref } from 'vue'
const items = ref(['keyboard', 'mouse', 'iPhone', 'macbook', 'adapter'])

// TODO: Add Code Here

const newItem = ref('')

function deleteItem(index) {
    items.value.splice(index, 1)
}

function add() {
    items.value.push(newItem.value)
    newItem.value= ''
}

</script>

<template>

    <h2>Shopping Cart</h2>
    <!-- TODO: Add Code Here -->
    <ul>
        <li v-for="(item,index) in items" :key="index">
            {{ item }}
            <!-- // if doing it inside can just have items.splice(index, 1) -->
            <!-- // if doing it outside, need to have items.value.splice(index, 1) -->
            <button @click="items.splice(index,1)">Delete</button>
            <!-- <button @click="deleteItem(index)">Delete</button> -->
        </li>
    </ul>
    <input type="text" v-model="newItem" @keyup.enter="add()">
    <button @click="items.push(newItem)">Add!</button>
    <!-- <button @click="add(newItem)">Add!</button> -->

</template>
