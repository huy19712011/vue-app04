<script setup>
import { ref } from "vue";
import { RouterLink, RouterView } from "vue-router";
const greeting = ref("Hello World");
import { onMounted } from "vue";

onMounted(() => {
  console.log("Component is mounted");
  setTimeout(() => {
    greeting.value = "Changed";
  }, 3000);
});
</script>

<template>
  <p>
    <input
      type="text"
      v-model="greeting"
    />
  </p>
  <p>{{ greeting }} ({{ greeting.length }})</p>
</template>
