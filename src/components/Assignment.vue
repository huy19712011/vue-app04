<script setup>
defineProps({
  assignment: Object,
});
</script>

<template>
  <div>
    <li>
      <label>
        {{ assignment.name }}
        <input
          type="checkbox"
          v-model="assignment.complete"
        />
      </label>
    </li>
  </div>
</template>
