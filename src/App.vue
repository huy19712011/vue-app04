<script setup>
import { computed, ref } from "vue";
import { RouterLink, RouterView } from "vue-router";
import { onMounted } from "vue";

const assignments = ref([
  { id: 1, name: "Finish project", complete: false },
  { id: 2, name: "Read chapter 4", complete: false },
  { id: 3, name: "Turn in homework", complete: false },
]);

const completedAssignments = computed(() => {
  return assignments.value.filter((assignment) => assignment.complete);
});
const inProgressAssignments = computed(() => {
  return assignments.value.filter((assignment) => !assignment.complete);
});
</script>

<template>
  <div class="center">
    <section v-show="inProgressAssignments.length">
      <h2>In Progress</h2>
      <ul>
        <li
          v-for="assignment in inProgressAssignments"
          :key="assignment.id"
        >
          <label>
            {{ assignment.name }}
            <input
              type="checkbox"
              v-model="assignment.complete"
            />
          </label>
        </li>
      </ul>
      <!-- <pre>
        {{ assignments }}
      </pre> -->
    </section>
    <section v-show="completedAssignments.length">
      <h2>Completed</h2>
      <ul>
        <li
          v-for="assignment in completedAssignments"
          :key="assignment.id"
        >
          <label>
            {{ assignment.name }}
            <input
              type="checkbox"
              v-model="assignment.complete"
            />
          </label>
        </li>
      </ul>
      <!-- <pre>
        {{ assignments }}
      </pre> -->
    </section>
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
