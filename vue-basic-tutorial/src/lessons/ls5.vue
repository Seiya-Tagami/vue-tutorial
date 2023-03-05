<template>
  <div>
    <input type="text" />
    <p>こんにちは</p>
  </div>
  <input type="checkbox" name="" id="" v-model="checked" />
  <div>checked: {{ checked }}</div>
  <textarea name="" id="" cols="30" rows="10" v-model="contents"></textarea>
  <button @click="submitForm(contents)" :disabled="!checked">提出</button>
</template>

<script setup>
import { ref } from "vue";

// const name = ref("");
const contents = ref("");
const checked = ref(false);

const submitForm = () => {
  alert(`フォームを提出しました。フォーム：${contents.value}`);
  contents.value = "";
};
</script>
