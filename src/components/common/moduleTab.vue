<template>
    <div class='module-tab-container'>
        <div class='module-left'>
            <slot name='module_left'></slot>
        </div>
        <div class='module-right'>
            <slot name='module_right'></slot>
        </div>
    </div>    
</template>
<script>
export default {
    
}
</script>
<style scoped>
.module-tab-container{
    height: 45px;
    display: flex;
    justify-content: space-between;
}
.module-tab-container a{
    margin-left: 30px;
    text-decoration: none;
}
.module-tab-container a:hover{
    color: #00a1d6;
}
.module-tab-container .tab-bar{
    display: inline-block;
    height: 20px;
    line-height: 20px;
    margin-left: 15px;
    cursor: pointer;
    border-bottom: 1px solid transparent;
}
.tab-bar:hover{
    color: #00a1d6;
    border-bottom: 1px solid #00a1d6;
}
.tab-selected{
    color: #00a1d6;
    border-bottom: 1px solid #00a1d6 !important;
}
.module-right{
    height: 100%;
}
</style>
