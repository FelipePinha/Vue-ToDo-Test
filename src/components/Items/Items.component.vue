<script setup lang="ts">
import type { ItemInterface } from '../../models/Items/Item.interface';

defineProps<{ Items: ItemInterface[] }>();

const emit = defineEmits<{ (e: 'changeItem', id: number): any }>();

const completeTodo = (id: number) => {
    emit('changeItem', id);
};
</script>

<template>
    <div>Item List</div>
    <ul v-for="data in Items" :key="data.id">
        <li>
            {{ data.name }} -
            <input type="checkbox" v-model="data.completed" @click="completeTodo(data.id)" />
        </li>
    </ul>
</template>
