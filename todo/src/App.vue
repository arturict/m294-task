<script setup>
import { ref, computed } from "vue";

const tasks = ref([

]);

const sortedTasks = computed(() => {
  return tasks.value.slice().sort((a, b) => {
    if (a.high_priority && !b.high_priority) return -1;
    if (!a.high_priority && b.high_priority) return 1;
    return 0;
  });
});

function addTask() {
  const task = document.getElementById("task").value;
  const prio = document.getElementById("prio").checked;
  const timeG = document.getElementById("timeGuess").value;
  tasks.value.push({
    text: task,
    done: false,
    high_priority: prio,
    timeGuess: timeG,
  });
  document.getElementById("task").value = "";
  document.getElementById("prio").checked = false;
  document.getElementById("timeGuess").value = "";
}
const amountDone = computed(
  () => tasks.value.filter((task) => task.done).length
);
const totalTasks = computed(() => tasks.value.length);
function deleteTask(index) {
tasks.value.splice(index, 1);
}
const timeRemaining = computed(() => {
  return tasks.value
    .filter((task) => !task.done)
    .reduce((acc, task) => acc + task.timeGuess, 0);
});
</script>

<template>
  <div class="container">
    <h2>Aufgabenliste</h2>

    <p>
      {{ amountDone }} von {{ totalTasks }} Tasks sind erledigt,
      {{ timeRemaining }}h Aufwand offen
    </p>

    <div class="form-group">
      <label for="task">Neuer Task</label>
      <input class="form-control" id="task" type="text" />
      <label for="timeGuess">Geschätzte Zeit</label>
      <input type="number" id="timeGuess" class="form-control" />
    </div>

    <label for="prio">
      <input id="prio" type="checkbox" />
      Hohe Priorität
    </label>

    <div class="form-actions">
      <button @click="addTask">Task hinzufügen</button>
    </div>

    <!-- <ul>
      <li
        v-for="(task, index) in sortedTasks"
        :key="index"
        :class="{ 'is-done': task.done, 'high-priority': task.high_priority }"
      >
        <input type="checkbox" name="done" v-model="task.done" />
        {{ task.timeGuess }} Stunden für   {{ task.text }} 
        <button @click="deleteTask(index)"> Löschen</button>
      </li>
    </ul> -->
    <table>
      <tr>
        <td>Priorität</td>
        <td>Aufgabe</td>
        <td>Geschätzte Zeit</td>
        <td>Löschen</td>
      </tr>

      <tr
        v-for="(task, index) in sortedTasks"
        :key="index"
        :class="{ 'is-done': task.done, 'high-priority': task.high_priority }"
      >
        <td><input type="checkbox" name="done" v-model="task.done" /></td>
        <td>{{ task.high_priority ? "Hoch" : "Normal" }}</td>
        <td>{{ task.text }}</td>
        <td>{{ task.timeGuess }}</td>
        <td><button @click="deleteTask(index)">Löschen</button></td>
      </tr>
    </table>
  </div>
</template>

<style>
.is-done {
  text-decoration: line-through;
}

.high-priority {
  font-weight: bold;
  color: red;
}

.form-group {
  display: block;
}

.form-group label {
  display: block;
  margin-bottom: 2px;
}

.form-control {
  width: 100%;
  padding: 2px 5px;
  height: 32px;
  margin-bottom: 5px;
}

.form-actions {
  display: block;
  margin-top: 1rem;
  margin-bottom: 2rem;
}

.container {
  margin: 20px auto;
  max-width: 400px;
  width: 100%;
}
</style>
