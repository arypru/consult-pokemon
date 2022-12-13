<script setup>
import {computed} from "vue";
import VCard from '/src/components/VCard.vue';
import PokemonTypes from '/src/json/PokemonTypes.json'

const pokemon = computed(() => PokemonTypes.pokemonTypes)

</script>

<template>
  <div class="flex flex-col justify-center">
    <img src="../public/logo.svg" class="h-24" alt="Pokemón App"/>
    <div class="mt-12 grid grid-cols-6 gap-7 place-content-around">
      <div v-for="pokemonType in pokemon">
        <VCard :pokemon-type="pokemonType"/>
      </div>
    </div>
  </div>
</template>


