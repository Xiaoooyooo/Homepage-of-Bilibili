<template>
    <div class='m-container'>
      <div class='new'>
          <i class='blbl-icon new-refresh'></i>
          <span><b>xxxx</b>条新动态</span>
      </div>
      <div class='more'>
          <span>更多</span>
          <span class='blbl-icon more-pic'></span>
      </div>
    </div>    
</template>
<script>
export default {
    
}
</script>
<style scoped>
.m-container > *{
    height: 100%;
    display: inline-block;
    border: 1px solid #ccd0d7;
    border-radius: 4px;
    height: 22px;
    line-height: 22px;
    padding: 0 10px;
    transition: all .2s;
}
.new{
  cursor: pointer;
  margin-right: 10px;
  transition: all 0.2s ease;
}
.new-refresh{
  display: inline-block;
  width:13px;
  height:13px;
  margin-right: 3px;
  vertical-align: middle;
  background-position: -475px -88px;
  transition: all 0.5s ease;
}
.new:hover{
  background-color: #ccd0d7;
}
.new:hover .new-refresh{
  transform: rotate(360deg);
}
.more{
  display: inline-block;
  cursor: pointer;
  transition: all 0.2s ease;
}
.more span{
  display: inline-block;
  transition: all 0.2s ease;
}
.more-pic{
  display: inline-block;
  width: 6px;
  height: 12px;
  margin-left: 3px;
  vertical-align: -2px;
  background-position: -478px -218px;
  transition: all 0.2s ease;
}
.more:hover{
  background-color: #ccd0d7;
}
.more:hover span{
  transform: translateX(-2px);
}
.more:hover .more-pic{
  transform: translateX(2px);
}
</style>
