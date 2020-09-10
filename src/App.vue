<template>
  <div id="app" class="w-full h-screen bg-blue-900 flex items-center justify-center">
    <div class="max-w-sm md:border md:border-gray-200 md:p-4 rounded-lg flex flex-col items-center justify-center">
      <div class="w-12 h-24 my-2 p-2 flex flex-col items-center justify-between border-2 border-blue-800 rounded-full shadow-inner">
        <div class="w-6 h-6 rounded-full bg-gray-900"></div>
        <div class="w-6 h-6 mt-2 rounded-full bg-gray-900"></div>
        <div class="w-6 h-6 mt-2 rounded-full bg-gray-900"></div>
      </div>
      <div class="bg-gray-900 py-1 px-2 my-2 text-gray-100 text-uppercase text-xs font-bold">VUEKIA</div>
      <div class="max-w-sm p-2 bg-gray-500 rounded-lg">
        <GameMain ref="game"/>
      </div>
      <div class="flex items-center w-full px-2">
        <div class="mt-2 w-4/12 flex flex-col px-2">
          <button class="h-10 rounded-full border-4 border-gray-900 bg-gray-300 shadow-lg px-2 text-uppercase text-xs font-bold"
            @click="togglePause"> {{ paused ? 'Continue' : 'Pause' }} </button>
          <button class="h-10 rounded-full border-4 border-gray-900 mt-2 bg-gray-300 shadow-lg px-2 text-uppercase text-xs font-bold"
            @click="restart"> Restart </button>
        </div>
        <div class="mt-2  ml-4 w-8/12 flex flex-wrap">
          <div class="w-1/3 h-10"></div>
          <div class="w-1/3 h-10 rounded-full bg-gray-300 border-4 border-gray-900 shadow-lg text-green-500 font-bold flex items-center justify-center"
            data-key="w"
            @click="toggleDirection">2 abc</div>
          <div class="w-1/3 h-10"></div>
          <div class="w-1/3 h-10 rounded-full bg-gray-300 border-4 border-gray-900 shadow-lg text-green-500 font-bold flex items-center justify-center"
            data-key="a"
            @click="toggleDirection">4 ghi</div>
          <div class="w-1/3 h-10"></div>
          <div class="w-1/3 h-10 rounded-full bg-gray-300 border-4 border-gray-900 shadow-lg text-green-500 font-bold flex items-center justify-center"
            data-key="d"
            @click="toggleDirection">6 mno</div>
          <div class="w-1/3 h-10"></div>
          <div class="w-1/3 h-10 rounded-full bg-gray-300 border-4 border-gray-900 shadow-lg text-green-500 font-bold flex items-center justify-center"
            data-key="s"
            @click="toggleDirection">8 tuv</div>
          <div class="w-1/3 h-10"></div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import GameMain from "./components/GameMain.vue";

export default {
  name: "App",

  data: function () {
    return({
      paused: false,
      crashed: false,
    })
  },

  components: {
    GameMain,
  },

  methods: {
    togglePause: function () {
      this.$refs.game.changePause()
      this.paused = ! this.paused
    },
    restart: function () {
      this.$refs.game.resetGame()
      this.crashed = ! this.crashed
    },
    toggleDirection: function (e) {
      this.$refs.game.setDirectionNext(e.srcElement.dataset.key)
    }
  },
   
};
</script>

<style>
@import "./assets/css/app.css";
</style>
