<script setup>
const props = defineProps({
  action: String,
});

const emit = defineEmits(["clicked"]);
const btnClick = () => {
  emit("clicked", props.action);
};
</script>

<template>
  <button @click.prevent="btnClick">{{ action }}</button>
</template>
