<template>
  <div id="app">
    <div class="app-wrap">
      <GameMain />
      <div>
        <hr />
        <h3>Vue.js Snake</h3>
        <p>
          This game was developed using Vue.js in a few hours.<br />You can
          check it out on <a href="https://github.com/Afshinb2/VueSnake">GitHub</a>.
        </p>
      </div>
    </div>
  </div>
</template>

<script>
import GameMain from "./components/GameMain.vue";

export default {
  name: "App",
  components: {
    GameMain,
  },
};
</script>

<style>
@import "./assets/css/app.css";
</style>
