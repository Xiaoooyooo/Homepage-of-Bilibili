<template>
    <ul class='tab-bar-container'>
      <li @click='changeIndex(index)' :class="{'tab-item':1,'tab-selected':selectedIndex == index}" v-for='(i,index) in 7' :key='index'>{{ day[index] }}</li>  
    </ul>    
</template>
<script>
export default {
    data(){
        return{
            day:['最新','一','二','三','四','五','六','七'],
            selectedIndex:0,
        }
    },
    methods:{
        changeIndex(i){
            this.selectedIndex = i
            this.$emit('changeTime',i)
        }
    }
}
</script>
<style scoped>
.tab-bar-container{
    flex: 1;
    display: flex;
    margin: 0 20px;
}
.tab-item{
    flex: 1;
    cursor: pointer;
    text-align: center;
    font-size: 18px;
    height: 34px;
    line-height: 34px;
    border-bottom: 1px solid #e5e9ef;
}
.tab-item:hover{
    color: #00a1d6;
    border-color: #00a1d6;
}
.tab-selected{
    color: #00a1d6;
    border-color: #00a1d6;
}
</style>
