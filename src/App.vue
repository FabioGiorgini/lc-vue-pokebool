<script>
import axios from 'axios';
import { store } from './store.js';
import AppHeader from './components/AppHeader.vue'
import AppMain from './components/AppMain.vue'

//URL da chiamare  https://raw.githubusercontent.com/Biuni/PokemonGO-Pokedex/master/pokedex.json'

export default {
  components: {
    AppHeader,
    AppMain
  },
  data(){
    return {
      store
    }
  },
  methods: {
    getPokemonFromApi() {
      axios.get ('https://raw.githubusercontent.com/Biuni/PokemonGO-Pokedex/master/pokedex.json')
      .then((response)=> {
      store.pokemonList = response.data.pokemon;
      store.pokemonFilteredList = store.pokemonList;

    })

    },
    filterPokemon(userInput) {
      store.pokemonFilteredList = store.pokemonList.filter((p)=>p.name.toLowerCase().includes(userInput))
    }
  },

  mounted() {
    this.getPokemonFromApi();
  }
}
</script>

<template>
  <AppHeader @searchPokemon="filterPokemon"></AppHeader>
  <AppMain></AppMain>
</template>

<style lang="scss">
  @use './style/generic.scss';
  @use './style/partials/variables' as *;


</style>
