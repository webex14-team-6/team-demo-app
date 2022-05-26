<template>
  <h1>Home</h1>
  <div class="links">
    <div class="link-button1">
      <router-link to="/quiz">Vueクイズ</router-link>
    </div>
    <div class="link-button2">
      <router-link to="/palette">Vueパレット</router-link>
    </div>
    <div class="link-button3">
      <router-link to="/memo">Vueメモ</router-link>
    </div>
  </div>
</template>

<style>
h1 {
  text-align: center;
  margin: 40px 0 30px;
}

a {
  text-decoration: none;
  color: black;
  font-weight: bold;
}

.links {
  width: 900px;
  height: 350px;
  margin: auto;
  background-color: #42b983;
  border-radius: 100px;
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 30px;
}

.link-button1 {
  width: 260px;
  height: 170px;
  background-image: url(../assets/e0724_1.svg);

  font-size: 30px;
  text-align: center;
  line-height: 160px;
}

.link-button2 {
  width: 230px;
  height: 220px;
  background-image: url(../assets/e0727_1.svg);

  font-size: 30px;
  text-align: center;
  line-height: 210px;
}

.link-button3 {
  width: 240px;
  height: 200px;
  background-image: url(../assets/e0180_1.svg);

  font-size: 30px;
  text-align: center;
  line-height: 190px;
}

.link-button1:hover {
  transform: scale(1.05);
}

.link-button2:hover {
  transform: scale(1.05);
}

.link-button3:hover {
  transform: scale(1.05);
}
</style>
