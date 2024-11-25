<script setup>
import Assignment from "./Assignment.vue";

defineProps({
  assignments: Array,
  title: String,
});
</script>

<template>
  <div>
    <section v-show="assignments.length">
      <h2>{{ title }}</h2>
      <ul>
        <Assignment
          v-for="assignment in assignments"
          :key="assignment.id"
          :assignment="assignment"
        >
        </Assignment>
      </ul>
    </section>
  </div>
</template>
