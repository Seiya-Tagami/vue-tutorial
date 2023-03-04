<script setup>
const weather = "晴れ";
const blogContents = "<h1>おはよ！</h1>";
const weatherToday = "weather-today";
const contentsId = "contentsId";
const isButtonDisabled = false;
let num = 3;

const clicked = () => {
  alert("Hi!");
};
</script>

<template>
  <p v-bind:class="weatherToday">今日の天気は{{ weather }}です</p>
  <div :id="contentsId" v-html="blogContents"></div>

  <p v-if="num % 2 === 0">偶数です。</p>
  <p v-else>奇数です。</p>
  <p>私は{{ isButtonDisabled ? 3 : 33 }}歳です。</p>
  <button :disabled="isButtonDisabled" @click="clicked">Button</button>
</template>

<style scoped>
.weather-today {
  color: blue;
}
</style>
