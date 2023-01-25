<script>
import axios from 'axios';
import { store } from './data/store'
import AppMain from './components/AppMain.vue'
import AppFilter from './components/AppFilter.vue'

export default {
  name: "App",
  data() {
    return {
      store,
      choice: '',
      apiUri: 'https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons',
      apiUriTyps: 'https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons/types1',

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
    },

    searchPokemonTyps() {
    },

    onChoiceClick(param) {
      this.choice = param;
      console.log(param)
      let url = `${this.apiUri}?q[type1]=${this.choice}`;
      console.log(url);
      this.fetchcard(url);
    },

    resetChoise() {
      let url = this.apiUri;
      this.fetchcard(url);
    },
    emits: ['choice-clicked', 'reset']
  },
  created() {
    this.fetchcard(this.apiUri)
    this.fetchtypes(this.apiUriTyps)
  },
  components: {
    AppMain,
    AppFilter,

  },

}
</script>

<template>
  <app-filter @choice-clicked="onChoiceClick" @reset="resetChoise"></app-filter>
  <app-main></app-main>
</template>

<style lang="scss">
@use './assets/style.scss'
</style>