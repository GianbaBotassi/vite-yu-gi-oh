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
        <option value="Noble Knight">Noble Knight</option>
        <option value="Alien">Alien</option>
        <option value="Pinni">Pinni</option>
        <option value="Renata">Renata</option>
    </select>
</template>


<style scoped lang="scss"></style>

