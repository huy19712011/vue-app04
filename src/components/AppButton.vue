<script setup>
import { ref, defineProps } from "vue";

defineProps({
  type: {
    type: String,
    default: "primary",
  },
  processing: {
    type: Boolean,
    default: false,
  },
});
</script>

<template>
  <button
    :class="{
      'border rounded': true,
      'btn btn-primary': type === 'primary',
      'btn btn-sencondary': type === 'secondary',
      'btn btn-light': type === 'muted',
    }"
    :disabled="processing"
  >
    Click me
  </button>
</template>
