<script setup lang="ts">
import { defineProps } from 'vue';

interface Props {
    title?: string;
    items: string[];
}

const { items } = withDefaults(defineProps<Props>(), {
    title: 'My List'
});
</script>

<template>
    <h2>{{ title }}</h2>
    <ul>

        {{ items }}
        <li v-for="(item, idx) in items" :key="idx">{{ item }}</li>
    </ul>
</template>