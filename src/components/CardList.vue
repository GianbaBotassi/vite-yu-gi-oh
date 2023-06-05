<script>
import { store } from '../store.js';


export default {
    name: "CardList",
    data() {
        return {
            store
        }
    }
}

</script>

<template>
    <div id="lista">
        <div id="card" v-for="card in store.CardArray" class="text-center">
            <img :src="card.card_images[0].image_url" alt="">
            <div class="name_card">{{ card.name }}</div>
            <div>{{ card.archetype }}</div>
        </div>
    </div>
</template>

<style scoped lang="scss">
@use 'styles/partials/mixins' as *;
@use 'styles/general' as *;

#lista {
    @include flex-content;
    flex-wrap: wrap;
    gap: 10px;

    #card {
        flex-basis: calc((100%/4) - 10px);
        gap: 25px 15px;
        padding: 30px 0;
        height: 300px;

        img {
            width: 100%;
            height: 100%;
            object-fit: contain;
        }
    }

    .name_card {
        font-size: 0.8rem;
    }
}
</style>
