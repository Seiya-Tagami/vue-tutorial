<script setup>
import { ref, onMounted } from "vue";
const count = ref(0);

const increment = () => {
  count.value++;
};

onMounted(() => {
  console.log(count);
  console.log(count.value);
});
</script>
<template>
  <button @click="increment">Count is: {{ count }}</button>
</template>
