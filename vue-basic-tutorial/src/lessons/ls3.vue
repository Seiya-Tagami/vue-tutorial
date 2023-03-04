<script setup>
import { reactive, computed, ref } from "vue";
const formState = reactive({
  email: "",
  name: "",
});

const lengthCheck = computed(() => {
  return formState.name.length >= 4 ? true : false;
});

const isBg = ref(false);

const toggleBg = () => (isBg.value = !isBg.value);
</script>
<template>
  <div :class="[isBg ? 'bg' : '']">
    <div>Emailを記入してください</div>
    <input type="text" v-model="formState.email" :placeholder="formState.email" />
    <p>名前を記入してください</p>
    <input type="text" v-model="formState.name" />
    <p>{{ formState.name.length }}文字入力中...</p>
    <div v-if="!lengthCheck" style="color: red; font-size: bold">文字は4文字以上で入力してください。</div>
    <button @click="toggleBg">背景の色を変更する</button>
  </div>
</template>

<style>
.bg {
  background-color: skyblue;
}
</style>
