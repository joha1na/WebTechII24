<script setup lang="ts">
import { ref } from 'vue';
import MyList from './components/MyList.vue';

const items = ref(['a', 'b', 'c']);
const items2 = ref(['d', 'e', 'f']);

const basis = ref(['a', 'b', 'c']);;
const basis2 = ref(['d', 'e', 'f']);

const text = ref('');

const add = () => {
  // console.log(text.value);
  if (text.value !== '') {
    items.value.push(text.value);
    items2.value.push(text.value);
    text.value = '';
  }
}

const reduce = () => {
  items.value.pop();
  items2.value.pop();
}

const refresh = () => {
  // console.log(items.value);
  // console.log(basis.value);
  items.value.splice(0);
  basis.value.forEach((item) => {
    // console.log(item);
    items.value.push(item);
  })
  items2.value.splice(0);
  basis2.value.forEach((item) => {
    // console.log(item);
    items2.value.push(item);
  })
}
</script>

<template>
  <div>
    <!-- {{ items }} -->

    <my-list :items="items" />
    <br>

    <my-list :items="items2" title="List 2" />
    <br>

    <input type="text" id="text" v-model="text">
    <p>{{ text }}</p>
    <button type="button" @click="add">Add</button>
    <button type="button" @click="reduce">Reduce</button>
    <button type="button" @click="refresh">Refresh</button>
  </div>
</template>
