<template>
    <div class='live-recommend-container'>
    <div class='swiper-container'>
        <ul class='live-recommend-swiper' :style="'left:'+slideLeft+'%'">
            <li>
                <img src="https://ss0.bdstatic.com/70cFuHSh_Q1YnxGkpoWK1HF6hhy/it/u=2435393964,661991470&fm=26&gp=0.jpg" alt="">
            </li>
            <li>
                <img src="https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1563897250781&di=7bc6cfca4f35d0d457e2d099660f68c2&imgtype=0&src=http%3A%2F%2Fb-ssl.duitang.com%2Fuploads%2Fitem%2F201412%2F17%2F20141217210558_VG8nF.thumb.1000_0.jpeg" alt="">
            </li>
            <li>
                <img src="https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1563897425126&di=c0331d62fd6f67f4bf23d91901482809&imgtype=0&src=http%3A%2F%2Fb-ssl.duitang.com%2Fuploads%2Fitem%2F201612%2F25%2F20161225092343_wR48k.jpeg" alt="">
            </li>
        </ul>        
    </div>
    <div class='live-recommend-anchor'>
        <a href="javascript:;">
            <img src="https://s1.hdslb.com/bfs/static/jinkela/home/asserts/wh.png" alt="">
        </a>
        <a href="javascript:;">
            <img src="https://s1.hdslb.com/bfs/static/jinkela/home/asserts/sp.png" alt="">
        </a>
    </div>
    </div>
</template>
<script>
import { setInterval, clearInterval } from 'timers';
export default {
    data(){
        return{
            slideLeft:0,
            timer:null
        }
    },
    activated(){
        if(!this.timmer)
            this.timer = setInterval(()=>{
            this.slideLeft -= 100
            if(this.slideLeft == -300)
            this.slideLeft = 0
            },3000)
    },
    deactivated(){
        if(this.timer)
            clearInterval(this.timer)
        this.timer = null
    }
}
</script>
<style scoped>
.live-recommend-container{
    position: absolute;
    height:100%;
    width:100%;
    padding-top:20px;
    box-sizing: border-box;
    background: lightcoral;
    display: flex;
    flex-wrap: wrap;
    align-content: space-between;
    overflow: hidden;
}
.swiper-container{
    border-radius: 5px;
    overflow: hidden;
}
.live-recommend-swiper{
    position: relative;
    width:100%;
    height:248px;
    display: flex;
    transition: all 0.5s ease;
}
.live-recommend-swiper li,
.live-recommend-swiper img{
    flex-shrink: 0;
    height:100%;
    width:100%;
}
.live-recommend-anchor{
    width:100%;
}
.live-recommend-anchor a{
    display: inline-block;
}
.live-recommend-anchor a:nth-child(1){
    float:left;
}
.live-recommend-anchor a:nth-child(2){
    float:right;
}
</style>
