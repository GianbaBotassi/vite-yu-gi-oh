<script>

import axios from 'axios'
import { store } from './store.js'

import AppHeader from './components/AppHeader.vue'
import AppFilter from './components/AppFilter.vue'
import CardList from './components/CardList.vue'

export default {
  components: {
    AppHeader,
    AppFilter,
    CardList
  },
  data() {
    return {
      store
    }
  },
  methods: {           //metodo per chiamata axios a API
    GetCards() {
      axios.get(store.apiURL).
        then((res) => {
          store.CardArray = res.data.data
        }).catch((err) => {
          console.log(err.message)
        })
    }
  },
  created() {
    this.GetCards()
  }
}
</script>

<template>
  <AppHeader />
  <main>
    <div class="container">
      <AppFilter />
      <CardList />
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
