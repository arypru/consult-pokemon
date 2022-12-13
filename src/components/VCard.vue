<script>

export default {
  props: {
    pokemonType: Object
  },

  computed: {
    backgroundBodyStyles() {
      return {
        '--bg-color': this.pokemonType.color,
      };
    }
  },
}
</script>

<template>
  <div :style="backgroundBodyStyles" class="card">
    <div class="card-content">
      <img :src="pokemonType.icon" class="h-16 mb-5" alt="type-pokemon"/>
      <p class="pointer-events-none text-2xl">{{ pokemonType.name }}</p>
    </div>
    <div class="card-background"></div> <!--b-->
  </div>
</template>

<style>
.card-background {
  position: fixed;
  z-index: -1;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  transition: .25s;
}


.card-content{
  display: grid;
  place-content: center;
  transition:.25s;
  height: 13rem;
  width: 13rem;
  background: var(--bg-color) !important
}

.card-content:hover {
  border: 0.2rem solid #e5e5e5 !important;
  border-radius: 2rem ;
  /*box-shadow: 0 20px 25px -5px rgb(0 0 0 / 0.1), 0 8px 10px -6px rgb(0 0 0 / 0.1);*/
  transition: 0.3s all ease-in-out;
  transform:scale(1.25);
}

.card-content:not(:hover){
  filter: brightness(0.8) saturate(1) contrast(1.2) blur(1.2px);
}

.card .card-content:first-child p img {
  background: var(--bg-color) !important;
}

.card .card-content:first-child:hover ~ .card-background {
  background: var(--bg-color);
}
</style>