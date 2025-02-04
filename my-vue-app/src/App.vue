<script setup>
import { ref } from 'vue'
const name = ref("???")
const prefixes = [
  'Hype',
  'Biz',
  'Lolz',
  'Rofl',
  'Galaxy',
  'Biz',
  'Fan',
  'Buzz',
  'Real',
  'Solid',
  'Inter',
  'Active',
  'Swoosh',
]

const suffixes = [
  'park',
  'span',
  'cloud',
  'loop',
  'verse',
  'layer',
  'er',
  'r',
  'dot',
  'dock',
  'space',
  'yard',
  'scale',
  'signal',
  'press',
  'ware',
  'port',
]
function generate() {
  const prefix = prefixes[Math.floor(Math.random() * prefixes.length)]
  const suffix = suffixes[Math.floor(Math.random() * suffixes.length)]
  name.value = prefix + suffix
}
</script>

<template>
<h1>Dein Startup heisst  </h1>
<p class="p">{{name}}</p>
<br>
<button @click="generate">Create</button>
</template> 

<style>
#app {
  text-align: center;
  }
  p{
    font-size: 20px;
    font-weight: bold;
    background-color: lightgray;
    padding: 10px;
    border-radius: 10px;
    border: gray 1px solid;
  }
</style>