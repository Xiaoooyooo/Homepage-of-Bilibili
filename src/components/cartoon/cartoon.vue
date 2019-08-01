<template>
  <div class="cartoon-container">
    <div class="left">
      <module-tab>
        <div slot="module_left">
          <i class="blbl-icon module-log log"></i>
          <span class="module-name">动画</span>
          <span
            @click="changeIndex(1)"
            :class="{'tab-bar':1,'tab-selected':selectedIndex == 1}"
            href="javascript:;"
          >有新动态</span>
          <span
            @click="changeIndex(2)"
            :class="{'tab-bar':1,'tab-selected':selectedIndex == 2}"
            href="javascript:;"
          >最新投稿</span>
        </div>
        <div slot="module_right">
          <more />
        </div>
      </module-tab>
      <transition name="tab-change" mode="out-in">
        <ul class="left-main" v-if="selectedIndex == 1" key="1">
          <vedio :showTab="true" v-for="i in 10" :key="i" />
        </ul>
        <ul class="left-main" v-else key="2">
          <vedio :showTab="true" v-for="i in 10" :key="i" />
        </ul>
      </transition>
    </div>
    <div class="right">
        <ranking/>
    </div>
  </div>
</template>
<script>
import moduleTab from "../common/moduleTab";
import more from "../common/moduleMore";
import vedio from "../common/video";
import ranking from '../common/vedioRanking'

export default {
  data() {
    return {
      selectedIndex: 1
    };
  },
  methods: {
    changeIndex(i) {
      this.selectedIndex = i;
    }
  },
  components: {
    moduleTab,
    more,
    vedio,
    ranking
  }
};
</script>
<style scoped>
.cartoon-container {
  width: 100%;
  display: flex;
}
.left {
  width: 900px;
  box-sizing: border-box;
  padding-right: 20px;
}
.log {
  background-position: -141px -908px;
}
.left-main {
  height: 320px;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  align-content: space-between;
}
.tab-checked {
}
.right {
  width: 260px;
}
</style>
