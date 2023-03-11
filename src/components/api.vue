<template>
  <button @click="fetchAPI">fetch api</button>
  <p>status: {{ status }}</p>
  <p>first data: {{ products[0] }}</p>
</template>

<script setup>
import axios from "axios";
import { ref } from "vue";

const status = ref("");
const products = ref([]);

async function fetchAPI() {
  const res = await axios.get("https://dummyjson.com/products"); //呼叫API
  status.value = res.status; // 拿出status code
  products.value = res.data.products; // 拿出data
}

</script>
