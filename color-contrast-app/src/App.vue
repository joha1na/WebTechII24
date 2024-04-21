<script setup lang="ts">
import { ref } from 'vue';
import MyList from './components/MyList.vue';

const items = ref(['a', 'b', 'c']);
const items2 = ref(['d', 'e', 'f']);

const text = ref('');

const add = () => {
  console.log(text.value);
  items.value.push(text.value);
  text.value = '';
}
</script>

<template>
  <div>

    {{ items }}

    <my-list :items="items" />

    <my-list :items="items2" title="List 2" />

    <input type="text" v-model="text">
    <p>{{ text }}</p>
    <button type="button" @click="add">Add</button>
  </div>
</template>
