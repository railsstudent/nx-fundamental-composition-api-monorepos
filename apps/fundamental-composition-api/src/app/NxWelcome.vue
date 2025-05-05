<script setup lang="ts">
import { ref } from 'vue';

const header = ref('Shopping List App')
const items = ref([
  { id: 1, label: '10 Apples' },
  { id: 2, label: '20 Bananas' },
  { id: 3, label: '5 Oranges' }
]);

const newItem = ref('');
const newItemHighPriority = ref(false);
const icecreamFlavors = ref<string[]>([])
</script>

<template>
  <div class="wrapper">
    <div class="container">
      <h1>{{ header || 'Welcome' }}</h1>
      <ul>
        <li v-for="{ id, label } in items" :key="id">
          {{ label }}
        </li>
      </ul>
      <input v-model.lazy="newItem" placeholder="Add new item" />
      <input type="checkbox" v-model="newItemHighPriority" />High Priority
      <br />
      <input type="checkbox" v-model="icecreamFlavors" value="vanilla" /> Vanilla
      <input type="checkbox" v-model="icecreamFlavors" value="chocolate chips" /> Cholocate Chips
      <input type="checkbox" v-model="icecreamFlavors" value="strawberry" /> Strawberry
    </div>
  </div>
</template>

<style scoped>
  input {
    padding: 0.25rem;
  }
</style>
