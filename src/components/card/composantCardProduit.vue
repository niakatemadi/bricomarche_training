<template>
  <div class="Container">
    <h1>Top produits</h1>
    <div class="Container-inner">
      <div class="Card">
        <div class="Card_top">
          <mark>Guide <br />Confort 2022</mark>
          <div class="Card_reduction"><p>60%</p></div>
        </div>
        <div class="Card_img"><img /></div>
        <div class="Card_information">
          <p>Karcher</p>
          <p>Nettoyeur haute pression k7</p>
          <p>369$</p>
          <p>Vendu par Bricomarché</p>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: 'card-component',
};
</script>
<style scoped>
.Container {
  display: flex;
  flex-direction: column;
  align-items: flex-end;
  background-color: #f7f7f5;
  width: 80vw;
  border: 1px solid blue;
  margin-top: 25px;
  margin-left: 9.3%;
  padding-top: 40px;
}
h1 {
  border: 1px solid red;
  width: 100%;
}
.Container-inner {
  border: 1px solid green;
  width: 75vw;
  height: 480px;
}
.Card {
  border: 1px solid purple;
  width: 300px;
  height: 460px;
  background-color: white;
}
.Card_img {
  height: 260px;
  background-color: blue;
}
p {
  margin-top: 20px;
  margin-left: 15px;
  text-align: start;
}
.Card_top {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0px;
  margin: 0px;
}
mark {
  text-align: start;
  background-color: grey;
  color: white;
  border: 3px solid grey;
}
.Card_reduction {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 40px;
  width: 40px;
  background-color: rgb(248, 183, 32);
  border-radius: 40px 0 40px 40px;
  color: white;
}
.Card_reduction p {
  border: 1px solid purple;
  margin-right: 15px;
  margin-bottom: 20px;
  font-weight: bold;
}
</style>
