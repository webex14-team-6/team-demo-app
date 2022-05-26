<template>
  <div class="links">
    <h1 class="home-title">Home</h1>
    <div class="icons">
      <img src="../assets/quiz-icon.svg" class="icon" />
      <img src="../assets/palette-icon.svg" class="icon" />
      <img src="../assets/memo-icon.svg" class="icon" />
    </div>
    <div class="buttons">
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
  </div>
</template>

<style>
.home-title {
  text-align: center;
  color: white;
}

a {
  text-decoration: none;
  color: white;
  font-weight: bold;
  font-size: 25px;
}

.links {
  width: 100%;
  height: 400px;
  margin: auto;
  padding: 50px 0;
  background-color: #42b983eb;
}

.icons {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 80px;
  margin: 40px 0 30px;
}

.icon {
  width: 150px;
  height: 150px;
}

.buttons {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 30px;
}

.link-button {
  width: 200px;
  height: 80px;
  border-radius: 10px;
  background-color: #2c3e50;
  box-shadow: 5px 5px white;

  text-align: center;
  line-height: 80px;
}

.link-button:hover {
  transform: scale(1.05);
}
</style>
