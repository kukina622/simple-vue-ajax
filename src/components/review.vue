<script setup>
import { ref } from "vue";
const counter = ref(0); // v-on
function add() {
  counter.value++;
}

const disableAdd = ref(false); // v-bind


// ----------------------------------------------------- //
const todo = ref(""); // v-model
const todolist = ref([]); // v-for
const visible = ref(true); // v-if

function appendTodolist() {
  todolist.value.push(todo.value);
}
</script>

<template>
  <h1>Vue review</h1>
  <h2>v-bind && v-on</h2>
  <button v-on:click="add" v-bind:disabled="disableAdd">add</button>
  <button @click="disableAdd = !disableAdd">toggle add</button>
  <p>counter : {{ counter }}</p>
  <hr />


  <h2>v-model && v-for && v-if </h2>
  <input type="text" v-model="todo" />
  <button @click="appendTodolist">append</button>
  <button @click="visible = !visible">toggle visible</button>

  <p>todo: {{ todo }}</p>
  <p>todolist</p>
  <ul v-if="visible">
    <li v-for="(t, i) in todolist" :key="i">
      {{ t }}
    </li>
  </ul>
</template>