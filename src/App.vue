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
    fetchcard(url) {
      axios.get(url)
        .then(res => {
          this.store.pokemon = res.data.docs;
        })
    }
  },
  created() {
    this.fetchcard(store.apiUri)
  },
  components: {
    AppMain,
  }
}

</script>

<template>
  <app-main></app-main>
</template>

<style lang="scss">
@use './assets/style.scss'
</style>