<script>
import { store } from '../store.js';
import SingleCard from './SingleCard.vue';

export default {
    components: {
        SingleCard
    },
    name: "CardList",
    data() {
        return {
            store
        }
    }
}

</script>

<template>
    <section class="p-4">
        <div id="card-list">
            <SingleCard v-for="card in store.cardArray" :details="card" :key="card.id" />
        </div>
    </section>
</template>

<style scoped lang="scss">
@use 'styles/partials/variables' as *;


section {
    background-color: white;

    #card-list {
        display: flex;
        flex-wrap: wrap;
        gap: 10px;
    }
}
</style>
