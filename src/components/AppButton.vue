<script setup>
import { ref } from "vue";

const processing = ref(false);
</script>

<template>
  <button
    class="bg-gray-200 hover: bg-gray-400 border rounded"
    :disabled="processing"
  >
    Click me
  </button>
</template>
