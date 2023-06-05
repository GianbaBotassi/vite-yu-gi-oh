<script>

import axios from 'axios'   //npm install axios
import { store } from './store.js'    //import store da store.js

import AppHeader from './components/AppHeader.vue'
import AppFilter from './components/AppFilter.vue'
import CardList from './components/CardList.vue'
import AppLoader from './components/AppLoader.vue'

export default {
  components: {
    AppHeader,
    AppFilter,
    CardList,
    AppLoader
  },
  data() {
    return {
      store
    }
  },
  methods: {           //metodo per chiamata axios
    GetCards() {
      axios.get(store.apiURL).
        then((res) => {
          store.CardArray = res.data.data;
          store.loading = false;
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
  <AppLoader v-if="store.loading" />
  <AppHeader />
  <main>
    <div class="cont py-2">
      <AppFilter class="my-2" />
      <CardList />
    </div>
  </main>
</template>

<style lang="scss">
@use 'styles/general' as *;
@use 'styles/partials/variables' as *;

main {
  background-color: $primary-bg;
}
</style>
