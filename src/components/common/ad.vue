<template>
    <div class='advertisement'>
        <img :src="imgsrc" alt="">
        <img src="https://s1.hdslb.com/bfs/static/jinkela/home/asserts/cm_2.png" alt="">
    </div>
</template>
<script>
export default {
    props:{
        imgsrc:String
    }
}
</script>

<style scoped>
    .advertisement{
        position: relative;
        height:96px;
        margin-bottom: 20px;
        overflow: hidden;
        border-radius: 5px;
    }
    .advertisement img:nth-child(1){
        height:100%;
        width:100%;
    }
    .advertisement img:nth-child(2){
        position: absolute;
        left:0;
        bottom:0;
    }
</style>
