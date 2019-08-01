<template>
    <div class='container'>
        <p style='text-align:left' class='tips'>登陆后你可以:</p>
        <div class='pic-container'>
            <img :style='"left:"+left+"px"' src="https://static.hdslb.com/images/danmu.png" alt="">
            <img :style='"left:"+left+"px"' src="https://static.hdslb.com/images/danmu.png" alt="">
        </div>
        <a class='btn-login' href="javascript:;">登陆</a>
        <p class='tips'>首次使用?<a href="javascript:;">点我去注册</a></p>
    </div>
</template>
<script>
import { setInterval } from 'timers';
export default {
    data(){
        return{
            left:0,
        }
    },
    mounted(){
        setInterval(()=>{
            if(this.left <= -320)
                this.left = 0
            this.left -= 3
        },50)
    }
}
</script>
<style scoped>
.container{
    position: absolute;
    z-index: 99;
    top:42px;
    padding:12px;
    width:320px;
    background: #fff;
    border:1px solid rgba(200,200,200,0.5);
}
.pic-container{
    /* height:200px;
    width:320px; */
    margin:12px 0;
    background: url('https://static.hdslb.com/images/base/danmu.png') no-repeat 0 0;
    background-size: cover;
    display: flex;
    overflow: hidden;
}
img{
    position: relative;
    height:200px;
    width:320px;
}
.btn-login{
    text-decoration: none;
    display: block;
    height: 43px;
    line-height: 43px;
    text-align: center;
    background: #00a1d6;
    border-radius: 4px;
    font-size: 14px;
    color: #fff;
}
.btn-login:hover{
    background: #00b5e5;
}
.tips{
    line-height: 12px;
    margin-top:8px;
    text-align: center;
}
.tips>a{
    margin:0 3px;
    color: #00a1d6;
}
.tips>a:hover{
    color:#00b5e5;
}
</style>
