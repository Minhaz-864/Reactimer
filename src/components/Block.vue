<template>
<div class="container">
  <div class="box " v-show= "isShown" @click="counter">
      Yolo
      </div>
      </div>
     <div v-if="this.reactionTime>0">{{reactionTime}}</div>
</template>

<script>
export default {
props:['delay'],
data(){
    return{
        isShown:false,
        reactionTime:0,
        timer:null
    }
},
methods:{
    startTimer(){
        this.timer = setInterval(()=>{
            this.reactionTime += 10;
        },10)

    },
    counter(){
        clearInterval(this.timer),
        this.$emit('endclick',this.reactionTime)
        console.log(this.reactionTime)
    }
},
mounted(){
    console.log("Is Mounted"),
    setTimeout(()=>{
        this.isShown = true;
        this.startTimer();
    },this.delay)
},
updated(){
    console.log("Updated")
},
unmounted(){
    console.log("Unmounted")
}
}
</script>

<style>
 .container div{
    width:400px;
    border-radius: 20px;
    background: #4ef0e3;
    color: #fff;
    text-align: center;
    padding:100px  0;
    margin:40px auto;
}

</style>