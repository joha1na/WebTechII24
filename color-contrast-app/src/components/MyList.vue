<script setup lang="ts">
import { defineProps } from 'vue';

interface Props {
    title?: string;
    items: string[];
}

const props = withDefaults(defineProps<Props>(), {
    title: 'My List'
});

const uppercaseTitle = props.title.toUpperCase();
</script>

<template>
    <h3>{{ uppercaseTitle }}</h3>
    <ul>
        <!-- {{ items }} -->
        <li v-for="(item, idx) in items" :key="idx">{{ item }}</li>
    </ul>
</template>