<script setup>
const count = ref(0);

function handleClick() {
  console.log("Before");
  setTimeout(() => console.log("Timeout"), 0);
  Promise.resolve().then(() => console.log("Promise"));
  console.log("After");
}
</script>

<template>
  <button @click="handleClick">Click me</button>
</template>
