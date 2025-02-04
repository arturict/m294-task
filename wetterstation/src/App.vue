<script setup>
import { ref, computed } from "vue";

const celsius = ref(10);
const fahrenheit = computed(() => {
  return (celsius.value * 9) / 5 + 32;
});
const kelvin = computed(() => {
  return celsius.value + 273.15;
});
const isFreezing = computed(() => {
  return celsius.value <= 0;
});
function change(amount) {
  celsius.value += amount;
}
</script>

<template>
  <h1>Wetterstation</h1>
  <table class="table">
    <tr>
      <th>Temperatur in Celsius</th>
      <td>{{ celsius }}°C</td>
    </tr>
    <tr>
      <th>Temperatur in Fahrenheit</th>
      <td>{{ fahrenheit }}°F</td>
    </tr>
    <tr>
      <th>Temperatur in Kelvin</th>
      <td>{{ kelvin }}K</td>
    </tr>
    <tr>
      <th>Gefrierpunkt unterschritten?</th>
      <td>{{ isFreezing ? "Ja" : "Nein" }}</td>
    </tr>
  </table>
  <div>
    <button @click="change(-1)">Es wird kälter</button>
    <button @click="change(1)">Es wird wärmer</button>
  </div>
</template>

<style>
body {
  text-align: center;
  font-family: sans-serif;
}
.table {
  width: 320px;
  margin: 20px auto;
}
.table th {
  text-align: left;
}
.table td {
  text-align: right;
}
button + button {
  margin-left: 20px;
}
</style>
