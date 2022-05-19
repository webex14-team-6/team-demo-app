<template>
  <h1>Home</h1>
  <div class="links">
    <div class="link-button">
      <router-link to="/quiz">Vueクイズ</router-link>
    </div>
    <div class="link-button">
      <router-link to="/palette">Vueパレット</router-link>
    </div>
    <div class="link-button">
      <router-link to="/memo">Vueメモ</router-link>
    </div>
  </div>
</template>

<style>
a {
  text-decoration: none;
  color: white;
}

.links {
  width: 100%;
  display: flex;
  justify-content: center;
  gap: 50px;
}

.link-button {
  width: 250px;
  height: 80px;
  background-color: #42b983;

  font-size: 30px;
  text-align: center;
  padding-top: 35px;

  box-shadow: 8px 8px 8px gray;
}

.link-button:hover {
  transform: scale(1.05);
}
</style>
