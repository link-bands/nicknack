<script setup>
import { onMounted, ref } from "vue";
// When using the Tauri API npm package:
import { invoke } from "@tauri-apps/api/tauri";

onMounted(() => {
  // console.log(a*b);
});

const myCustomCommand = () => {
  const a = 0.07;
  const b = 100;
  invoke('my_custom_command', { a, b }).then((message) => console.log(message));
};
</script>

<template>
  <button @click="myCustomCommand">触发rust方法</button>
</template>
