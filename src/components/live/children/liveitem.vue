<template>
    <ul class='live-item-container'>
        <li class='live-item' v-for='i in 10' :key='i'>
            <a class='item-content' href="javascript:;">
                <div class='live-cover'>
                    <img src="https://b-ssl.duitang.com/uploads/item/201807/11/20180711153154_nBJcX.jpeg" alt="">
                    <img src="https://b-ssl.duitang.com/uploads/item/201803/04/20180304024915_jrhRy.jpeg" alt="">
                    <div class='live-title'>
                        <span class='live-host'>
                            主持人主持人主持人主持人主持人
                        </span>
                        <span class='viewers'>
                            <i class='viewer'></i>
                            xxxx
                        </span>
                    </div>
                </div>
                <div class='live-details'>
                    <p class='live-name'>直播名直播名直播名直播名直播名直播名直播名</p>
                    <p class='live-class'>类型</p>
                </div>
            </a>
        </li>
    </ul>
</template>
<script>
export default {
    
}
</script>
<style scoped>
.live-item-container{
    height:100%;
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
    align-content: space-between;
}
.live-item{
    height:148px;
    width: 160px;
}
.item-content{
    display: block;
    height:100%;
    text-decoration: none;
    overflow: hidden;
}
.live-cover{
    height: 100px;
    width: 160px;
    position: relative;
    border-radius: 4px;
    overflow: hidden;
}
.live-cover img{
    position: absolute;
    height:100%;
    width: 100%;
    transition: all 0.3s ease;
}
.live-cover img:nth-child(1){
    opacity: 1;
}
.live-cover img:nth-child(2){
    opacity: 0;
}
.item-content:hover .live-cover img:nth-child(1){
    opacity: 0;
}
.item-content:hover .live-cover img:nth-child(2){
    opacity: 1;
}
.live-cover .live-title{
    position: absolute;
    bottom:0;
    width:100%;
    height: 34px;
    background: linear-gradient(transparent,transparent,rgba(0,0,0,.5));
    color: #fff;
    transition: all 0.3s ease;
}
.live-title span{
    line-height: 20px;
    position: absolute;
    bottom: 0;
}
.live-title span:nth-child(1){
    left: 4px;
}
.item-content:hover .live-title{
    opacity: 0;
}
.viewers{
    right:4px;
}
.live-host{
    display: inline-block;
    width:50%;
    overflow: hidden;
    white-space: nowrap;
    text-overflow: ellipsis;
}
.live-details{
    position: relative;
    padding-top: 8px;
    height: 40px;
    line-height: 20px;
}
.live-name{
    height:100%;
    overflow: hidden;
    text-overflow: ellipsis;
    color: #222;
}
.live-class{
    position: absolute;
    bottom: 0;
    width:100%;
    height:20px;
    background-color: #fff;
    color:#9ba3ab;
    transition: all 0.3s ease;
}
.item-content:hover .live-class{
    bottom:-100%;
}
</style>
