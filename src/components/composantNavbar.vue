<template>
  <header>
    <div class="Header__blocOne">
      <div class="Header__blocOne__searchBar">
        <input
          @click="inputFocus"
          :class="{ focus: isInputFocused }"
          placeholder="Vous recherchez un outil, un conseils, un service ?"
        />
      </div>
      <ul>
        <li>
          <img src="../assets/help.png" />
          <span>Aide</span>
        </li>
        <li><img src="../assets/moncomte.png" /> <span>Mon compte</span></li>
        <li><img src="../assets/heart.png" /><span>Favoris</span></li>
        <li><img src="../assets/panier.png" /><span>Panier</span></li>
      </ul>
    </div>
    <div class="Header__blocTwo">
      <div class="Header__blocTwo__logo">
        <img
          src="https://www.bricomarche.com/_ui/responsive/theme-bricoMarche/assets/img/logo.svg"
        />
      </div>
      <div class="Header__blocTwo__toggleBtn" @click="displaynav">
        <span></span><span></span>
      </div>
      <nav :class="{ active: displayNav, 'text-danger': hasError }">
        <ul>
          <li>PRODUITS</li>
          <li>CONSEILS</li>
          <li>SERVICES</li>
          <li>PROJETS</li>
          <li>GUIDE CONFORT</li>
        </ul>
      </nav>
      <p>Trouver votre magasin</p>
    </div>
  </header>
</template>

<script>
export default {
  name: 'navBar',
  data() {
    return {
      displayNav: false,
      isInputFocused: false,
    };
  },
  methods: {
    displaynav() {
      this.displayNav = !this.displayNav;
    },
    inputFocus() {
      this.isInputFocused = !this.isInputFocused;
    },
  },
};
</script>
<style scoped>
.Header__blocOne {
  display: flex;
  flex-flow: row wrap;
  justify-content: space-between;
  padding-left: 10%;
  padding-right: 10%;
  border-bottom: 1px solid rgb(215, 215, 215);
}
.Header__blocOne ul {
  display: flex;
  flex-direction: row;
  justify-content: space-around;
  list-style: none;
  padding: 0;
  width: 25vw;
}
.Header__blocOne__searchBar input {
  width: 25vw;
  height: 35px;
  border-radius: 30px;
  border: 0.5px solid black;
}
.Header__blocOne__searchBar input.focus {
  background-color: red;
}
.Header__blocTwo {
  display: flex;
  flex-flow: row wrap;
  justify-content: space-between;
  align-items: flex-end;
  padding-left: 10%;
  padding-right: 10%;
  border-bottom: 1px solid rgb(215, 215, 215);
  height: 100px;
}
.Header__blocTwo__logo {
  margin-bottom: 30px;
}
.Header__blocTwo p {
  text-decoration: underline;
}
.Header__blocTwo nav {
  width: 50vw;
  font-weight: bolder;
  color: grey;
}
.Header__blocTwo nav ul li {
  margin-left: 2px;
  margin-right: 2px;
}
.Header__blocTwo ul {
  display: flex;
  flex-direction: row;
  justify-content: space-around;
  list-style: none;
  padding: 0;
}
li:hover {
  cursor: pointer;
  color: black;
  transition: 0.3s;
}

@media (max-width: 500px) {
  .Header__blocOne {
    display: none;
  }
  .Header__blocTwo {
    flex-direction: row-reverse;
    padding-left: 3%;
  }
  .Header__blocTwo nav {
    position: absolute;
    left: -100%;
    top: 20%;
    width: 95%;
  }
  .Header__blocTwo nav ul {
    display: flex;
    flex-direction: column;
    height: 30vh;
  }
  .Header__blocTwo nav.active {
    position: absolute;
    left: 0%;
    top: 20%;
    transition: 0.5s;
    height: 88vh;
  }
  .Header__blocTwo p {
    display: none;
  }
  .Header__blocTwo__toggleBtn {
    background-color: black;
    width: 30px;
    height: 30px;
  }
}
</style>
