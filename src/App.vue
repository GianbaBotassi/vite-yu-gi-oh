<script>
import AppHeader from './components/AppHeader.vue'
import AppFilter from './components/AppFilter.vue'

export default {
  components: {
    AppHeader,
    AppFilter
  }
}
</script>

<template>
  <AppHeader />
  <main>
    <div class="container">
      <AppFilter />

    </div>
  </main>
</template>

<style lang="scss">
@use 'styles/general' as *;
@use 'styles/partials/variables' as *;

main {
  background-color: coral;
}
</style>
