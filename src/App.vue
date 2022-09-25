<template>
  <div id="app">
    <navBar />
    <composantCarousel :slides="slides" />
  </div>
</template>

<script>
import navBar from './components/composantNavbar.vue';
import composantCarousel from './components/carousel/composantCarousel.vue';

export default {
  name: 'App',
  components: {
    navBar,
    composantCarousel,
  },
  data() {
    return {
      players: [],
      slides: [
        'https://picsum.photos/id/1032/900/400',
        'https://picsum.photos/id/1033/900/400',
        'https://picsum.photos/id/1037/900/400',
        'https://picsum.photos/id/1036/900/400',
        'https://picsum.photos/id/1035/900/400',
      ],
    };
  },
  mounted() {
    const headers = {
      'Content-Type': 'application/json',
    };
    fetch('https://fr.dofus.dofapi.fr/weapons/14084', { headers })
      .then((response) => response.json())
      .then((data) => console.log('new dofus datas', data));
  },
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@200&display=swap');
#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  font-family: 'Roboto', sans-serif;
}
</style>
