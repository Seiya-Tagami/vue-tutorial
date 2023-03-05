<script setup>
import { ref } from "vue";

const isLoad = ref(false);
const data = [
  {
    color: "red",
    value: "#f00",
  },
  {
    color: "green",
    value: "#0f0",
  },
  {
    color: "blue",
    value: "#00f",
  },
];
</script>
<template>
  <button v-on:click.prevent="isLoad = !isLoad">データを読み込む</button>
  <div v-if="isLoad">
    <div v-for="(datum, index) in data" :key="datum.color">
      <li :style="{ color: datum.value }">{{ index }}・{{ datum.color }}</li>
    </div>
  </div>
  <div v-else>No Data</div>
</template>
