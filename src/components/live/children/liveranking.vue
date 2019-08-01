<template>
        <ul class='live-ranking'>
            <li class='live-ranking-item' v-for='i in 6' :key='i'>
                <a href="javascript:;">
                    <span :class="{'ranking-num':1,'top-3':i < 4}">{{i}}</span>
                    <i class='pic'>
                        <img src="https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1563879964264&di=ceff0e0c2a1fbc59080156afba7fdd8a&imgtype=0&src=http%3A%2F%2Fimg4.duitang.com%2Fuploads%2Fitem%2F201610%2F30%2F20161030111603_m5hYr.jpeg" alt="">
                    </i>
                    <div class='live-item-title'>
                        <p>直播人</p>
                        <p>直播标题</p>
                    </div>
                    <div class='live-popularity'>
                        <i></i>
                        <span>人气</span>
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
.live-ranking{
    padding-top:20px;
    box-sizing: border-box;
    height:100%;
    width:100%;
    position: absolute;
    display: flex;
    /* flex-direction: column; */
    flex-wrap: wrap;
    align-content: space-between;
}
.live-ranking-item{
    width:260px;
    height:40px;
}
.live-ranking-item a{
    text-decoration: none;
    padding-left: 25px;
    box-sizing: border-box;
    display: block;
    height:100%;
    width:100%;
    position: relative;
    display: flex;
    justify-content: space-between;
    align-items: center;
}
.ranking-num{
    color:#fff;
    text-align: center;
    line-height: 18px;
    font-weight:bolder;
    background-color: #b8c0cc;
    height:18px;
    width:18px;
    border-radius: 4px;
    position: absolute;
    left:0;
    top:0;
}
.top-3 {
    background-color: #f25d8e;
}
.live-ranking-item .pic{
    display: inline-block;
    height:40px;
    width:40px;
    border-radius: 50%;
    overflow: hidden;
}
.pic img{
    height:100%;
    width:100%;
}
.live-item-title{
    flex: 1;
    height:100%;
    padding:0 10px;
    overflow: hidden;

}
.live-item-title p{
    line-height: 16px;
    margin:2px 0;
    color: #222;
    white-space: nowrap;
    text-overflow: ellipsis;
}
.live-item-title p:nth-child(2){
    color:#99a2aa;
}
.live-item-title p:nth-child(1){
    transition: all 0.3s ease;
}
.live-item-title:hover p:nth-child(1){
    color:#00a1d6;
}
.live-popularity{
    color:#99a2aa;
}
.live-popularity i{
    display: inline-block;
    vertical-align: middle;
    width: 12px;
    height: 12px;
    margin-top: -2px;
    margin-right: 3px;
    background: url(//s1.hdslb.com/bfs/static/jinkela/home/asserts/live-eye.png) no-repeat;
}
</style>
