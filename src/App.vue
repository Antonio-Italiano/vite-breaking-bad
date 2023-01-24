<script>
import axios from 'axios';
import AppMain from './components/AppMain.vue'
export default {
  name: "App",
  data() {
    return {
      pokemon: [],
    }
  },
  methods: {
    fetchcard() {
      axios.get('https://rickandmortyapi.com/api/character')
        .then(res => {
          this.pokemon = res.data.results;
        })
    }
  },
  created() {
    this.fetchcard()
  },
  components: {
    AppMain,
  }
}

</script>

<template>
  <app-main :pokemon="pokemon"></app-main>
</template>

<style lang="scss">
@use './assets/style.scss'
</style>