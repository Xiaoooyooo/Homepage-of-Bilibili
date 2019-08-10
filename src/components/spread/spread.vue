<template>
  <div class="spread">
    <div class="left">
      <module-tab>
        <div slot='tab_left'>
          <i class="blbl-icon module-log log"></i>
          <a href='javascript:;' class="module-name">推广</a>
          <a class='module-tips' href="javascript:;">笔记本电脑天天抽！</a>
        </div>
      </module-tab>
      <ul class="left-content">
        <vedio v-for='i in 5' :key='i' />
      </ul>
    </div>
    <div class="right">
      <div class="people">
        <span>在线人数：6253578</span>
        <em></em>
        <span>最新投稿：108135</span>
      </div>
      <a href="javascript:;" class="right-body"></a>
    </div>
  </div>
</template>
<script>
import vedio from '../common/video'
import moduleTab from '../common/moduleTab'
export default {
  components:{
    vedio,
    moduleTab
  }
};
</script>
<style scoped>
.spread {
  height: 213px;
  width: 1160px;
  min-width: 980px;
  margin: 0 auto 13px;
}
.left {
  float: left;
  width: 900px;
  box-sizing: border-box;
  padding-right: 20px;
}
.log {
  background-position: -141px -75px;
}
.people {
  margin-bottom: 11px;
  width: 260px;
  height: 34px;
  line-height: 34px;
  color: #6d757a;
  background: #e5e9ef;
  border-radius: 4px;
  display: flex;
  justify-content: space-around;
  align-items: center;
}
.people em {
  border-left: 1px solid #b8c0cc;
  height: 13px;
}
.left-body {
  margin: 0 auto 13px;
  width: 900px;
  display: flex;
  justify-content: space-between;
}
.left-content {
  width: 100%;
  display: flex;
  justify-content: space-between;
}
.right{
  float: right;
  height: 100%;
}
.right-body {
  display: block;
  height: 150px;
  width: 260px;
  background: url("https://i0.hdslb.com/bfs/archive/b4f060515051ef5b9f2cf1a396325279c20695ad.jpg")
    no-repeat 0 0;
  background-size: cover;
  border-radius: 4px;
}
</style>