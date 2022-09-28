<template>
  <div class="container">
    <div class="container-inner">
      <button v-for="(item, index) in buttons" :key="`item-${index}`">
        <div class="btn-effect">
          <a>{{ item }}</a>
        </div>
        {{ item }}
      </button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'nav-button',
  props: ['buttons'],
};
</script>
<style scoped>
.container {
  display: flex;
  justify-content: center;
}
.container-inner {
  display: flex;
  flex-flow: row wrap;
  justify-content: space-around;
  width: 60vw;
  margin-top: 8px;
}
button {
  width: 290px;
  height: 60px;
  border-radius: 8px;
  color: #7f9fa8;
  background-color: white;
  margin-top: 20px;
  border: 1px solid #7f9fa8;
  position: relative;
}
button:hover {
  cursor: pointer;
}
.btn-effect {
  background-color: #7f9fa8;
  position: absolute;
  top: -0.5%;
  bottom: 0;
  left: 0;
  right: 99%;
  color: white;
  opacity: 0;
  display: flex;
  justify-content: center;
  align-items: center;
  border-radius: 7px;
}
button:hover .btn-effect {
  right: -0.5%;
  transition: 0.3s ease-in-out;
  opacity: 1;
}
a {
  transform: scale(0);
}
.btn-effect:hover a {
  transform: scale(1);
  transition: 0.15s 0.15s;
}
</style>
