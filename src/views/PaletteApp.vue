<template>
  <h1>Vue パレット</h1>
  <div class="app">
    <div
      class="palette"
      style="background-color: rgba(0, 50, 0, 0.5)"
      v-on:mousemove="changeColor"
      v-on:click="pickColor"
      v-bind:style="paletteStyle"
    ></div>
    <p>rgba( {{ this.red }}, 50, {{ this.green }}, 0.8 )</p>
    <div class="colors-container">
      <div
        v-for="(color, index) in colors"
        :key="index"
        class="mini-palette"
        v-bind:style="{
          backgroundColor: `rgba(${color.red}, 50, ${color.green}, 0.5)`,
        }"
        v-on:click="showColor(color)"
      ></div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      red: 0,
      green: 0,
      colors: [
        // { red: 0, green: 0 }
      ],
    }
  },

  methods: {
    // マウスの位置に応じて色を変える
    changeColor(e) {
      this.red = e.offsetX
      this.green = e.offsetY
    },
    // 色を選んでミニパレットに追加する
    pickColor() {
      const newColor = {
        red: this.red,
        green: this.green,
      }
      this.colors.push(newColor)
    },
    // パレットに指定した色を表示する
    showColor(color) {
      this.red = color.red
      this.green = color.green
    },
  },

  computed: {
    paletteStyle() {
      return {
        backgroundColor: `rgba(${this.red}, 50, ${this.green}, 0.8)`,
      }
    },
  },
}
</script>

<style>
.app {
  display: flex;
  width: 100%;
  flex-direction: column;
  align-items: center;
}
.palette {
  width: 255px;
  height: 255px;
  border-radius: 3%;
  box-shadow: 2px 2px 5px #718ca7c9;
}
.mini-palette {
  min-width: 60px;
  height: 60px;
  border-radius: 50%;
  filter: brightness(110%) saturate(120%);
  margin: 4px;
}

.colors-container {
  display: flex;
  flex-wrap: wrap-reverse;
  width: 410px;
  padding: 10px;
  background-color: rgb(233, 194, 170);
  border-radius: 20px;
}
</style>
