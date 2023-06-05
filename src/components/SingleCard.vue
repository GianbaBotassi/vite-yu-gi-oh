<script>
import { store } from '../store.js';


export default {
    name: "SingleCard",
    props: {
        details: Object
    }
}

</script>

<template>
    <div id="card" class="text-center">
        <img :src="details.card_images[0].image_url" :alt="details.name">
        <div class="name_card fw-bold text-white">{{ details.name }}</div>
        <div>{{ details.archetype }}</div>
    </div>
</template>

<style scoped lang="scss">
@use 'styles/partials/variables' as *;

#card {
    flex-basis: calc((100%/5) - 10px);
    margin-bottom: 10px;
    background-color: $primary-bg;

    .name_card {
        font-size: 0.7rem;
        margin: 5px 0;
        height: 50px;
    }
}
</style>
