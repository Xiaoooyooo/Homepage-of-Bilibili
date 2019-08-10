<template>
  <div class="module-container">
      <div class="module-left">
        <module-tab>
          <div slot='tab_left'>
            <i class="blbl-icon module-log log"></i>
            <a href='javascript:;' class="module-name">正在直播</a>
            <span class="live-total">
              当前共有
              <span>xxxx</span>个在线直播
            </span>
            <a class='module-tips' href="javascript:;">
              <i class="blbl-icon fire-pic"></i>
              <span>233秒居然能做这些</span>
            </a>
          </div>
          <div slot='tab_right'>
            <more />
          </div>
        </module-tab>
        <div class="module-left-main">
          <live-item />
        </div>
      </div>
      <div class="module-right">
        <div class="right-top">
          <a @click='changeTab(1)' :class="{'blbl-tab-item':1,on:liveTabIndex == 1}" href="javascript:;">直播排行</a>
          <a @click='changeTab(2)' :class="{'blbl-tab-item':1,on:liveTabIndex == 2}" href="javascript:;">关注的主播</a>
          <a @click='changeTab(3)' :class="{'blbl-tab-item':1,on:liveTabIndex == 3}" href="javascript:;">为你推荐</a>
        </div>
        <div class="right-bot">
          <transition name='live-tab'>
            <keep-alive>
              <component :is='liveTab'/>
            </keep-alive>
          </transition>
        </div>
      </div>
  </div>
</template>
<script>
import liveranking from './children/liveranking'
import aoa from './children/aoa'
import recommend from './children/recommend'
import liveItem from './children/liveitem'
import moduleTab from '../common/moduleTab'
import more from '../common/moduleMore'

export default {
  data(){
    return{
      liveTabIndex:1,
      liveTab:'liveranking'
    }
  },
  methods:{
    changeTab(i){
      this.liveTabIndex = i
      switch (i){
        case 1:
          this.liveTab = 'liveranking'
          break
        case 2:
          this.liveTab = "aoa"
          break
        case 3:
          this.liveTab = 'recommend'
          break
        default:
          break
      }
    }
  },
  components: {
    liveranking,
    aoa,
    recommend,
    liveItem,
    moduleTab,
    more
  }
};
</script>
<style scoped>
/* 动画 */
.live-tab-enter{
  transform: translateX(-100%);
}
.live-tab-leave-to{
  transform: translateX(100%);
}
.live-tab-enter-active,
.live-tab-leave-active{
  transition: all 0.5s ease;
}

.log {
  background-position: -141px -652px;
}
.live-total {
  margin-left: 20px;
}
.live-total span{
  color: #00a1d6;
}
.fire-pic{
  display: inline-block;
  height:14px;
  width:14px;
  background-position: -665px -1113px;
}
.right-bot {
  position: relative;
  flex-grow: 1;
  flex-shrink: 0;
  width:260px;
  height:324px;
  overflow: hidden;
}
</style>
