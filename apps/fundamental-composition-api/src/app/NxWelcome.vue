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
// const icecreamFlavors = ref<string[]>([])

const saveItem = () => {
  items.value.push({ id: items.value.length + 1, label: newItem.value });
  newItem.value = '';
};

</script>

<template>
  <div class="wrapper">
    <div class="container">
      <h1>{{ header || 'Welcome' }}</h1>
      <ul>
        <li v-for="{ id, label } in items" :key="id">
          {{id}} - {{ label }}
        </li>
      </ul>
      <form @submit.prevent="saveItem()">
        <input v-model.trim="newItem"  placeholder="Add new item" />
        <input type="checkbox" v-model="newItemHighPriority" />High Priority
        <button class="btn btn-primary">Save Item</button>
      </form>
      <!-- <br />
      <input type="checkbox" v-model="icecreamFlavors" value="vanilla" /> Vanilla
      <input type="checkbox" v-model="icecreamFlavors" value="chocolate chips" /> Cholocate Chips
      <input type="checkbox" v-model="icecreamFlavors" value="strawberry" /> Strawberry -->
    </div>
  </div>
</template>

<style scoped>
  input {
    padding: 0.25rem;
  }
</style>
