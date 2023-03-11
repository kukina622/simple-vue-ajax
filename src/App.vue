<script setup>
import axios from "axios";
import { ref } from "vue";

const products = ref([]);

async function fetchAPI() {
  const res = await axios.get("https://dummyjson.com/products");
  products.value = res.data.products;
}

</script>

<template>
  <button @click="fetchAPI">fetch api</button>
  <p>{{ products[0] }}</p>
</template>
