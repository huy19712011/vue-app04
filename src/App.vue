<script setup>
import { ref } from "vue";
import { RouterLink, RouterView } from "vue-router";
import { onMounted } from "vue";

const buttonClasses = ref(["text-green"]);
const active = ref(false);
const toggle = () => {
  // buttonClasses.value = "text-red";
  active.value = !active.value;
};
</script>

<template>
  <div class="center">
    <button
      :class="active ? 'text-red' : 'text-green'"
      @click="toggle"
    >
      Click me
    </button>
  </div>
</template>

<style scoped>
body {
  display: grid;
  place-items: center;
}

.center {
  display: grid;
  place-items: center;
}

.text-red {
  color: red;
}

.text-green {
  color: green;
}
</style>
