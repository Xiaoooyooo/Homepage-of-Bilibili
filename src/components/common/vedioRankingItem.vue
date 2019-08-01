<template>
    <ul class='ranking-item-container'>
        <li class='ranking-item' v-for='(i,index) in 7' :key='index'>
            <span :class="{'ranking-item-index':1,'top-3':index < 3}">{{index + 1}}</span>
            <a class='ranking-item-title' href='javascript:;'>一些文字说明</a>
        </li>    
    </ul>
</template>
<script>
export default {
    props:{
        items:{
            type:Array,
            default(){
                return []
            }
        }
    }
}
</script>
<style scoped>
.ranking-item-container{
    height: 100%;
    display: flex;
    flex-wrap: wrap;
    align-content: space-between;
    margin-bottom: 20px;
}
.ranking-item{
    flex: 1 0 auto;
    width: 100%;
}
.ranking-item-index{
    display: inline-block;
    height: 18px;
    width: 18px;
    text-align: center;
    line-height: 18px;
    font-weight: bolder;
    color: #fff;
    border-radius: 4px;
    background-color: #b8c0cc;
}
.top-3{
    background-color: #f25d8e;
}
.ranking-item-title{
    margin-left: 10px;
    white-space: nowrap;
    overflow: hidden;
    text-decoration: none;
    color: #222;
}
.ranking-item-title:hover{
    color: #00a1d6;
}
</style>
