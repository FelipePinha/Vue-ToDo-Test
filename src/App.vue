<script setup lang="ts">
import ItemList from './components/Items/Items.component.vue';

const ItemsList: any = [
    {
        id: 1,
        name: 'Coffee',
        completed: false,
    },
    {
        id: 2,
        name: 'Books',
        completed: false,
    },
];
</script>

<template>
    <div>
        <h1>My ToDo</h1>
    </div>
    <ItemList :Items="ItemsList"></ItemList>
</template>
