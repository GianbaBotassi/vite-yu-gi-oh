<script>
export default {
    name: "AppLoader"
}
</script>

<template>
    <div class="loading-page">
        <span class="loader"></span>
    </div>
</template>

<style scoped lang="scss">
@use 'styles/partials/mixins' as *;
@use 'styles/partials/variables' as *;
@use 'styles/general' as *;


.loading-page {
    position: fixed;
    top: 0;
    left: 0;
    @include flex-content(center);
    flex-direction: column;
    width: 100%;
    height: 100%;
    background-color: $white-bg;
}

.loader {
    color: #000;
    font-size: 10px;
    width: 1em;
    height: 1em;
    border-radius: 50%;
    position: relative;
    text-indent: -9999em;
    animation: mulShdSpin 1.3s infinite linear;
    transform: translateZ(0);
}

@keyframes mulShdSpin {

    0%,
    100% {
        box-shadow: 0 -3em 0 0.2em,
            2em -2em 0 0em, 3em 0 0 -1em,
            2em 2em 0 -1em, 0 3em 0 -1em,
            -2em 2em 0 -1em, -3em 0 0 -1em,
            -2em -2em 0 0;
    }

    12.5% {
        box-shadow: 0 -3em 0 0, 2em -2em 0 0.2em,
            3em 0 0 0, 2em 2em 0 -1em, 0 3em 0 -1em,
            -2em 2em 0 -1em, -3em 0 0 -1em,
            -2em -2em 0 -1em;
    }

    25% {
        box-shadow: 0 -3em 0 -0.5em,
            2em -2em 0 0, 3em 0 0 0.2em,
            2em 2em 0 0, 0 3em 0 -1em,
            -2em 2em 0 -1em, -3em 0 0 -1em,
            -2em -2em 0 -1em;
    }

    37.5% {
        box-shadow: 0 -3em 0 -1em, 2em -2em 0 -1em,
            3em 0em 0 0, 2em 2em 0 0.2em, 0 3em 0 0em,
            -2em 2em 0 -1em, -3em 0em 0 -1em, -2em -2em 0 -1em;
    }

    50% {
        box-shadow: 0 -3em 0 -1em, 2em -2em 0 -1em,
            3em 0 0 -1em, 2em 2em 0 0em, 0 3em 0 0.2em,
            -2em 2em 0 0, -3em 0em 0 -1em, -2em -2em 0 -1em;
    }

    62.5% {
        box-shadow: 0 -3em 0 -1em, 2em -2em 0 -1em,
            3em 0 0 -1em, 2em 2em 0 -1em, 0 3em 0 0,
            -2em 2em 0 0.2em, -3em 0 0 0, -2em -2em 0 -1em;
    }

    75% {
        box-shadow: 0em -3em 0 -1em, 2em -2em 0 -1em,
            3em 0em 0 -1em, 2em 2em 0 -1em, 0 3em 0 -1em,
            -2em 2em 0 0, -3em 0em 0 0.2em, -2em -2em 0 0;
    }

    87.5% {
        box-shadow: 0em -3em 0 0, 2em -2em 0 -1em,
            3em 0 0 -1em, 2em 2em 0 -1em, 0 3em 0 -1em,
            -2em 2em 0 0, -3em 0em 0 0, -2em -2em 0 0.2em;
    }
}
</style>
