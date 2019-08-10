<template>
    <ul class='module-left-main fanju-list-container'>
     <li class='fanju-item' v-for='(i,index) in 12' :key='index'>
         <a class='fanju-cover' href="javascript:;">
            <img src="https://ss1.bdstatic.com/70cFvXSh_Q1YnxGkpoWK1HF6hhy/it/u=2721362973,1840344704&fm=26&gp=0.jpg" alt="">
         </a>
         <div class='fanju-details'>
            <a class='fanju-name' href="javascript:;">番剧名番剧名番剧名番剧名番剧名番剧名番剧名</a>
            <a class='fanju-update' href="javascript:;">第n话</a>
         </div>
     </li>
    </ul>    
</template>
<script>
export default {
    props:{
        fanjuList:{
            type:Array,
            default(){
                return[]
            }
        }
    }
}
</script>
<style scoped>
.fanju-list-container{
    height: 420px;
}
.fanju-item{
    height: 75px;
    width: 180px;
    margin: 15px 0;
    display: flex;
}
.fanju-cover{
    height: 75px;
    width: 75px;
    border-radius: 4px;
    overflow: hidden;
}
.fanju-cover img{
    height: 100%;
    width: 100%;
}
.fanju-details{
    margin-left: 15px;
    display: inline-block;
    width: 90px;
}
.fanju-name{
    margin-bottom: 15px;
    text-decoration: none;
    display: block;
    height: 40px;
    line-height: 20px;
    text-overflow: ellipsis;
    overflow: hidden;
    color: #222;
}
.fanju-update{
    text-decoration: none;
    display: inline-block;
    padding: 0 4px;
    height: 20px;
    line-height: 20px;
    color: #fff;
    border-radius: 9px;
    background-color: #ff8eb3;
}
</style>
