<template>
  <h1>Vue クイズ</h1>
  <div id="quiz-app">
    <img class="quiz-image" src="@/assets/elizabeth.png" alt="クイズイメージ" />
    <div class="quiz-content">
      <h2 class="quiz-text">Q. {{ quiz.text }}</h2>
      <div class="buttons">
        <button
          v-for="(choice, i) in quiz.choices"
          v-bind:key="i"
          v-on:click="choiced(choice)"
        >
          {{ choice.text }}
        </button>
      </div>
      <div class="feedback">{{ feedback }}</div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      feedback: "",
      quiz: {
        text: "現在のイギリスの女王はエリザベス何世？",
        choices: [
          {
            text: "１世",
            feedback: "残念！世界史で有名な大英帝国の女王が１世だよ。",
          },
          {
            text: "２世",
            feedback: "正解！ちなみに今年で９６歳だよ！",
          },
          {
            text: "３世",
            feedback: "残念！まだ存在してないよ。",
          },
        ],
      },
    }
  },
  methods: {
    choiced(choice) {
      this.feedback = choice.feedback
    },
  },
}
</script>

<style scoped>
#quiz-app {
  width: 1000px;
  height: 500px;
  margin: auto;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
}

h1 {
  text-align: center;
}

.quiz-image {
  width: 600px;
  height: 420px;
  object-fit: contain;
}

.quiz-content {
  width: 350px;
  height: 300px;
}

.quiz-text {
  font-size: 30px;
  display: inline-block;
  padding-bottom: 10px;
  border-bottom: solid 1px #2c3e50;
}

.buttons {
  width: 300px;
  height: 70px;
  display: flex;
  align-items: center;
  padding: 1em;
  justify-content: space-around;
}

#quiz-app button {
  width: 80px;
  height: 40px;
  background-color: #42b983;
  color: white;
  border: 0;
  border-radius: 40px;
  box-shadow: 2px 2px 5px #2c3e50c9;
}

#quiz-app button:hover {
  transform: scale(1.05);
  background-color: #2dd388;
}

.feedback {
  padding: 20px;
  font-size: 18px;
}
</style>
