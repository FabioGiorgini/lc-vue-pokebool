<script>
export default {
    methods: {
        search() {
            if(this.userInput.length > 3) {
                this.$emit('searchPokemon', this.userInput)
            }
        }
    },
    data() {
        return {
            userInput: '',
        } 
    }
}
</script>

<template>
    <h1>POKEDEX</h1>
    <div class="input-group mb-3">
        <input v-model="userInput" @input="search" type="text" class="form-control" placeholder="Cerca Pokemon" aria-label="Recipient's username"
            aria-describedby="button-addon2">
        <button class="btn btn-outline-secondary" type="button" id="button-addon2">Reset</button>
        
    </div>
</template>

<style>
</style>