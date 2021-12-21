<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <h1>Reaction Timer Game</h1>
  <button @click= "play" v-bind:disabled="isPlaying">Play Reactime</button>
  <Block v-if = "isPlaying"  v-bind:delay="delay" @endclick= "endGame"/>
  <Results v-bind:result="result" v-show="showResult" v-if = "!isPlaying"/>
</template>

<script>

import Block from './components/Block.vue'
import Results from './components/Results.vue'

export default {
  name: 'App',
  components: {
     Block, Results
  },
  data(){
    return{
      isPlaying: false,
      delay: null,
      result:null,
      showResult: false
    }
  },
  methods:{
    play(){
      this.delay = 2000 + Math.random() * 8000;
      console.log(this.delay);
      this.isPlaying = true; 
    },
    endGame(endInterval){
      this.result = endInterval,
      this.isPlaying= false,
      this.showResult = true
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
