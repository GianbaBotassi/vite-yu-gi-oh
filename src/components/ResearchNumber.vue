<script>
import { store } from '../store.js';

export default {
    name: "ResearchNumber",
    data() {
        return {
            store
        }
    },
    computed: {
        numberCards() {
            return store.cardArray.length
        }
    }
}
</script>

<template>
    <div v-if="numberCards > 0" class="p-2 fw-bold">Found {{ numberCards }} cards</div>
    <div v-else class="p-2 fw-bold">No results found for {{ store.selectOption }}</div>
</template>


<style scoped lang="scss">
@use 'styles/partials/variables' as *;

div {
    background-color: $dark-grey-bg;
    color: $white-font;
}
</style>

