<template>
  <div class="vedio-ranking-container">
    <div class="vedio-ranking-head">
      <span class="ranking-title">排行</span>
      <span
        @mouseover="changeIndex(1)"
        :class="{'ranking-type':1,'ranking-type-selected':selectedIndex == 1}"
      >全部</span>
      <span
        @mouseover="changeIndex(2)"
        :class="{'ranking-type':1,'ranking-type-selected':selectedIndex == 2}"
      >原创</span>
      <div class="ranking-options">
        <p class="time-range">
          {{t1}}
          <i class="blbl-icon time-icon"></i>
        </p>
        <p @click="changeTime" class="time-range hide">{{t2}}</p>
      </div>
    </div>
    <div class="vedio-ranking-list">
      <keep-alive>
        <transition name='tab-change' mode='out-in'>
          <ranking-item v-if="selectedIndex == 1" key="one" />
          <ranking-item v-else key="two" />
					<!-- <button v-if="selectedIndex == 1" key="one">one</button>
					<button v-else key="two">two</button> -->
        </transition>
      </keep-alive>
    </div>
    <a href="javascript:;" class="moreInfo">
      查看更多
      <i class="blbl-icon arrow-right"></i>
    </a>
  </div>
</template>
<script>
import rankingItem from "./vedioRankingItem";

export default {
  data() {
    return {
      selectedIndex: 1,
      t1: "三日",
      t2: "一周"
    };
  },
  methods: {
    changeIndex(i) {
      this.selectedIndex = i;
    },
    changeTime() {
      [this.t1, this.t2] = [this.t2, this.t1];
    }
  },
  components: {
    rankingItem
  }
};
</script>
<style scoped>
.vedio-ranking-container {
  height: 100%;
  display: flex;
  flex-direction: column;
}
.vedio-ranking-list {
  flex: 1;
  margin-bottom: 15px;
  width: 100%;
}
.ranking-item {
  width: 100%;
}
.vedio-ranking-head {
  height: 45px;
}
.ranking-title {
  font-size: 20px;
  font-weight: 500;
}
.ranking-type {
  cursor: pointer;
  display: inline-block;
  border-bottom: 1px solid transparent;
  margin-left: 15px;
  height: 20px;
  line-height: 20px;
}
.ranking-type-selected {
  border-bottom: 1px solid #00a1d6;
}
.ranking-options {
  float: right;
  position: relative;
  top: 8px;
  border: 1px solid #ccd0d7;
  line-height: 22px;
  border-radius: 4px;
}
.time-range {
  padding: 0 7px;
}
.hide {
  display: none;
  cursor: pointer;
}
.hide:hover {
  background-color: #f6f6f6;
}
.ranking-options:hover .hide {
  display: block;
}
.time-icon {
  display: inline-block;
  width: 12px;
  height: 6px;
  margin-left: 5px;
  background-position: -475px -157px;
}
.moreInfo {
  height: 24px;
  line-height: 24px;
  text-decoration: none;
  color: #222;
  border-radius: 4px;
  text-align: center;
  background-color: #e5e9ef;
  border: 1px solid #e0e6ed;
  transition: all 0.3s ease;
}
.moreInfo:hover {
  background-color: #ccd0d7;
  border-color: #ccd0d7;
}
.arrow-right {
  vertical-align: middle;
  display: inline-block;
  background-position: -478px -218px;
  width: 6px;
  height: 12px;
}
</style>
