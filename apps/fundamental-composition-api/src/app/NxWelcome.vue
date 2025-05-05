<script setup lang="ts">
import { ref } from 'vue';

const name = ref('Vue 3 Composition API')

</script>

<template>
  <div class="wrapper">
    <div class="container">
      <div id="welcome">
        <h1>Hello, {{ name }}</h1>
        Input: <input v-model="name" />
      </div>
    </div>
  </div>
</template>

<style scoped>
  input {
    padding: 0.25rem;
  }
</style>
