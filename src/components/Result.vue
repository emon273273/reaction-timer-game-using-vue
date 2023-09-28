<template>
    <h1 > Your Reaction time is : {{ score }}ms</h1>
    <p class="rank">{{ rank }}</p>
</template>

<script>
export default {
props:['score'],
data(){

    return{

        rank:null
    }
},mounted(){

    if(this.score<250){
        this.rank="You are Ninja"
    }else if(this.score<400){
        this.rank="You are master"
    }else{
        this.rank=" You are Noob"
    }
}
}
</script>

<style>
.rank{

    font-size: 1.4rem;
    color:#0faf87;
    font-weight: bold;
}
</style>