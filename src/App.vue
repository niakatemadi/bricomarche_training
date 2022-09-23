<template>
  <div id="app">
    <navBar />
  </div>
</template>

<script>
import navBar from './components/composantNavbar.vue';

export default {
  name: 'App',
  components: {
    navBar,
  },
  data() {
    return {
      players: [],
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
