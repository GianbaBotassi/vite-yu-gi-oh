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
        <div id="founded" class="p-2 fw-bold">Found 20 cards</div>
        <div id="card-list">
            <SingleCard v-for="card in store.CardArray" :details="card" :key="card.id" />
        </div>
    </section>
</template>

<style scoped lang="scss">
@use 'styles/partials/variables' as *;


section {
    background-color: white;

    #founded {
        background-color: $dark-grey-bg;
        color: $white-font;
    }

    #card-list {
        display: flex;
        flex-wrap: wrap;
        gap: 10px;
    }
}
</style>
