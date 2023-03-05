<template>
  <BattleTitle />
  <div>
    <p>敵のHP: {{ enemyHP }}</p>
    <p>ヒーローの:{{ heroHP }}</p>
    <BattleBtn action="攻撃" @clicked="clicked" />
    <BattleBtn action="守備" @clicked="clicked" />
    <p>{{ msg }}</p>
  </div>
</template>

<script setup>
import { ref, watch } from "vue";
import BattleBtn from "./components-ls6/BattleBtn.vue";
import BattleTitle from "./components-ls6/BattleTitle.vue";

const enemyHP = ref(100);
const heroHP = ref(40);
const msg = ref("");
const msgClass = ref("");

const attack = () => {
  enemyHP.value = enemyHP.value - Math.floor(Math.random() * 10);
  heroHP.value = heroHP.value - Math.floor(Math.random() * 5);
  msg.value = "";
};

watch(heroHP, (curHP, prevHP) => {
  console.log(curHP, prevHP);
  if (curHP < 20) {
    msg.value = "HPが半分を切った...";
  }
  if (prevHP - curHP > 3) {
    msg.value = "会心の一撃を食らった";
  }
});

const clicked = (type) => {
  // console.log(type);
  type === "攻撃" && attack();
};
</script>
