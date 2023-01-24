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
      axios.get('https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons?per=10&page=1')
        .then(res => {
          this.pokemon = res.data.docs;
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