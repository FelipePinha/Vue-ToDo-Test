<script setup lang="ts">
defineProps<{ Items: any[] }>();
</script>

<template>
    <div>Item List</div>
    <ul v-for="data in Items" :key="data.id">
        <li>{{ data.name }}</li>
    </ul>
</template>
