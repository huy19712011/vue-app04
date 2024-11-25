<script setup>
import { ref } from "vue";

const newAssignment = ref("");

const emit = defineEmits(["add"]);

const add = () => {
  emit("add", newAssignment.value);
  newAssignment.value = "";
};
</script>

<template>
  <form @submit.prevent="add">
    <input
      placeholder="New assignment..."
      v-model="newAssignment"
    />
    <button type="submit">Add</button>
  </form>
</template>

<style scoped></style>
