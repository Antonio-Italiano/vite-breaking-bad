<script>
import axios from 'axios';
import { store } from './data/store'
import AppMain from './components/AppMain.vue'
export default {
  name: "App",
  data() {
    return {
      store
    }
  },
  methods: {
    // CREATE POKEMON ARRAYS
    fetchcard(url) {
      axios.get(url)
        .then(res => {
          this.store.pokemon = res.data.docs;
        })
    },

    // CREATE TYPES1 ARRAYS
    fetchtypes(url) {
      axios.get(url)
        .then(res => {
          this.store.types1 = res.data;
        })
    }
  },
  created() {
    this.fetchcard(store.apiUri)
    this.fetchtypes(store.apiUriTyps)
  },
  components: {
    AppMain,
  }
}
</script>

<template>
  <app-main>
  </app-main>
</template>

<style lang="scss">
@use './assets/style.scss'
</style>