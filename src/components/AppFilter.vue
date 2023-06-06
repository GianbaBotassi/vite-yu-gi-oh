<script>
import { store } from '../store.js';

export default {
    name: "AppFilter",
    data() {
        return {
            store
        }
    }
}
</script>

<template>
    <select v-model="store.selectOption" @change="$emit('changeOption')" name="type">
        <option value="All" selected>All</option>
        <option v-for="arch in store.archetypeArray" :key="arch.id">
            {{ arch.archetype_name }}
        </option>
    </select>
</template>


<style scoped lang="scss"></style>

