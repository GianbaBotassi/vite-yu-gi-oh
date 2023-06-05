<script>

export default {
    name: "AppHeader"
}

</script>

<template>
    <header>
        <div>
            <img src="/img/logo.jpg" alt="">
        </div>
        <h1>Yu-Gi-Oh Api</h1>

    </header>
</template>

<style scoped lang="scss">
@use 'styles/partials/mixins' as *;
@use 'styles/general' as *;


header {
    @include flex-content(start);
    margin-left: 20px;


    div {
        height: 50px;
        width: 50px;
    }
}
</style>
