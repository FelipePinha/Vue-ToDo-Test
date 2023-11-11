<script setup lang="ts">
import ItemList from './components/Items/Items.component.vue';
import type { ItemInterface } from './models/Items/Item.interface';
import { reactive, computed } from 'vue';

const ItemsList: ItemInterface[] = reactive([
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
    {
        id: 3,
        name: 'Notes',
        completed: false,
    },
    {
        id: 4,
        name: 'Social',
        completed: false,
    },
    {
        id: 5,
        name: 'Games',
        completed: false,
    },
]);

const completeTodo = (id: number) => {};

const completedAll = computed(() => {
    let all = ItemsList.length;
    let countComplete = 0;

    ItemsList.forEach((element: ItemInterface) => {
        if (element.completed) {
            countComplete++;
        }
    });
    return countComplete == all ? '[ All todo is completed ]' : '[ No ]';
});
</script>

<template>
    <div>
        <h1>My ToDo</h1>
        <h3>{{ completedAll }}</h3>
    </div>
    <ItemList :Items="ItemsList" @changeItem="completeTodo"></ItemList>
</template>
