<template>
  <div class="block" v-if="showBlock" @click="stoptimer">click me</div>
</template>

<script>
export default {
  props: ["delay"],

  data() {
    return {
      showBlock: false,
      timer:null,
      ractiontime:0
    };
  },
  mounted() {
    setTimeout(() => {
      this.showBlock = true;

      this.starttimer()
      console.log(this.delay);
    }, this.delay);
  },
  methods:{

    starttimer(){
this.timer=setInterval(()=>{

  this.ractiontime+=10
},10)
    },
    stoptimer(){
clearInterval(this.timer)
console.log(this.ractiontime)
this.$emit('end',this.ractiontime)

    }
  }
};
</script>

<style>
.block {
  width: 400px;
  border: radius 20px;
  background: #0faf87;
  color: white;
  text-align: center;
  padding: 100px 0;
  margin: 40px auto;
}
</style>