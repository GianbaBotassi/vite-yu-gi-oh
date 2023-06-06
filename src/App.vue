<script>

import axios from 'axios'   //npm install axios
import { store } from './store.js'    //import store da store.js

import AppHeader from './components/AppHeader.vue'
import AppFilter from './components/AppFilter.vue'
import CardList from './components/CardList.vue'
import AppLoader from './components/AppLoader.vue'
import ResearchNumber from './components/ResearchNumber.vue'

export default {
  components: {
    AppHeader,
    AppFilter,
    CardList,
    AppLoader,
    ResearchNumber
  },
  data() {
    return {
      store
    }
  },
  methods: {           //metodo per chiamata axios
    getCards() {
      store.apiURL = 'https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0';  //reset del API url

      if (store.selectOption !== "All") {
        store.apiURL = `${store.apiURL}?archetype=${store.selectOption}`
      }
      console.log(store.apiURL);
      console.log(store.selectOption);

      axios.get(store.apiURL).
        then((res) => {
          store.cardArray = res.data.data;
          store.loading = false;
        }).catch((err) => {
          console.log(err.message)
        })
    }
  },
  created() {
    this.getCards()
  }
}
</script>

<template>
  <AppLoader v-if="store.loading" />
  <div v-else>
    <AppHeader />
    <main>
      <div class="cont py-2">
        <AppFilter @changeOption="getCards" />
        <ResearchNumber />
        <CardList />
      </div>
    </main>
  </div>
</template>

<style lang="scss">
@use 'styles/general' as *;
@use 'styles/partials/variables' as *;

main {
  background-color: $primary-bg;
}
</style>
