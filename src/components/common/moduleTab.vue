<template>
    <div class='module-tab-container'>
        <div class='tab-left'>
            <slot name='tab_left'></slot>
            <slot name='center_tab_bar'></slot>
        </div>
        <div class='tab-right'>
            <slot name='tab_right'></slot>
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
.tab-left{
    flex: 1;
    display: flex;
}
.tab-right{
    height: 100%;
}
</style>
