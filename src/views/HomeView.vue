<script setup lang="ts">
import { ref } from 'vue'

const text = ref('')

const update = () => {
  fetch('http://127.0.0.1:8000/text/')
    .then((data) => data.json())
    .then((data) => {
      text.value = data
    })
}


setInterval(() => {
  update()
}, 1000);

</script>

<template>
  {{ text }}
</template>
