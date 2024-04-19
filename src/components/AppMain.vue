<script>
import PokemonCard from './PokemonCard.vue'
import { store } from '../store.js';
export default {
    components: {
    PokemonCard
  },
  data() {
        return {
            store
        }
    }
}

</script>

<template>
<div>PLACEHOLDER POKEMON PREFERITI</div>
<div>PLACEHOLDER POKEMON TIPO ELETTRO VISIBILE</div>
<div>PLACEHOLDER POKEMON TIPO PSICO VISIBILE</div>
<div>NUMERO POKEMON TROVATI: {{ store.pokemonFilteredList.length }} / {{ store.pokemonList.length }}</div>
<ul id="poke-list" class="list-group list-group-horizontal flex-wrap">
    <PokemonCard v-for="pokemon in store.pokemonFilteredList" :cardInfo="pokemon" :key="pokemon.id"></PokemonCard>
</ul>
</template>

<style>
</style>