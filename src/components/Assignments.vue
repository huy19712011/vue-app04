<script setup>
import { ref, computed } from "vue";
import AssignmentList from "./AssignmentList.vue";
import AssignmentCreate from "./AssignmentCreate.vue";
const assignments = ref([
  { id: 1, name: "Finish project", complete: false },
  { id: 2, name: "Read chapter 4", complete: false },
  { id: 3, name: "Turn in homework", complete: false },
]);

// const completed = computed(() => {
//   return assignments.value.filter((assignment) => assignment.complete);
// });
// const inProgress = computed(() => {
//   return assignments.value.filter((assignment) => !assignment.complete);
// });

const newAssignment = ref("");

const filters = computed(() => {
  return {
    inProgress: assignments.value.filter((assignment) => !assignment.complete),
    completed: assignments.value.filter((assignment) => assignment.complete),
  };
});

const add = (newAssignment) => {
  assignments.value.push({
    id: assignments.value.length + 1,
    name: newAssignment,
    complete: false,
  });
};
</script>

<template>
  <div class="center">
    <AssignmentList
      :assignments="filters.inProgress"
      title="In Progress"
    >
    </AssignmentList>
    <AssignmentList
      :assignments="filters.completed"
      title="Completed"
    >
    </AssignmentList>
    <AssignmentCreate @add="add"></AssignmentCreate>
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
