<template>
  <div class="box">
     Reaction Time: {{result}} ms
  </div>
</template>

<script>
export default {
    props:['result']

}
</script>

<style>
.box{
    width:400px;
    border-radius: 20px;
    background: #a908c9;
    color: #fff;
    text-align: center;
    padding:50px  0;
    margin:40px auto;
}

</style>