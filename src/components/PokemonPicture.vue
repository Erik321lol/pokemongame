<template>
    <div class="pokemon-container"></div>
    <img
        v-if="showPokemon"
        :src="imgSrc"
        class="fade-in"
        alt="pokemon">   
    <img
        v-else
        :src="imgSrc"
        class="hidden-pokemon"
        alt="pokemon">
  </template>
<script>
export default {
    props: {
        pokemonId: {
            type: Number,
            required: true
        },
        showPokemon: {
            type: Boolean,
            require: true,
            default: false
        }
    },
    computed: {
        imgSrc() {
            return `https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/dream-world/${this.pokemonId}.svg`
        }
    }
}
</script>
<style scoped>
/* Pokemon Picture */

img {
    height: 200px;
    user-select: none;
    -moz-user-select: none;
    -ms-user-select: none;
    -webkit-user-drag: none;
    -webkit-user-select: none;
}

.hidden-pokemon {
    filter: brightness(0);
}




</style>

