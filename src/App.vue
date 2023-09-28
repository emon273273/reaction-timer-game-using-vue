<template>
  <h1>Rapid Click Fire </h1>
  <button @click="start" :disabled="isplaying===true"> start</button>
  <BlockComponent v-if="isplaying" :delay="delay" @end="endgame"/>

<Result v-if="showresutl" :score="score"/>
</template>


<script>
import Result from "./components/Result.vue";
import BlockComponent from "./components/BlockComponent.vue"
export default {
  name: "App",
  components: {BlockComponent,Result},

  data(){
return{

  isplaying:false,
  delay: null,
  score:null,
  showresutl:false
}

  },

  methods: {
    start() {

      this.isplaying=true,
      this.delay=2000+Math.random()*5000
      this.showresutl=false
    },

    endgame(ractiontime){
      this.score=ractiontime
      this.isplaying=false;
      this.showresutl=true;

    }
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #444;
  margin-top: 60px;
}
button{
  background: #0faf87;
  color: white;
  border: none;
  padding: 8px 16px;
  border-radius: 4px;
  font-size: 16px;
  letter-spacing: 1px;
  cursor: pointer;
  margin: 10px;

}

button[disabled]{

  opacity: 0.2;
  cursor: not-allowed;
}
</style>
