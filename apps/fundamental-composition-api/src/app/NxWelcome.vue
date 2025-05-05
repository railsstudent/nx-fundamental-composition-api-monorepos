<script setup lang="ts">
import { ref } from 'vue';

const header = ref('Shopping List App')

</script>

<template>
  <div class="wrapper">
    <div class="container">
      <div id="welcome">
        <h1>{{ header || 'Welcome' }}</h1>
      </div>
    </div>
  </div>
</template>

<style scoped>
  input {
    padding: 0.25rem;
  }
</style>
