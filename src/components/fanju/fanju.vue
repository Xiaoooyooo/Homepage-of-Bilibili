<template>
  <div class="module-container">
    <div class="module-left">
      <module-tab>
        <div slot="tab_left">
          <i
            :class="{'blbl-icon':1,'module-log':1,'log-fj':fanjuType == 0,'log-gc':fanjuType == 1}"
          ></i>
          <a href="javascript:;" class="module-name">{{ title }}</a>
        </div>
        <tab-bar @changeTime="changeTime" slot="center_tab_bar" />
        <div slot="tab_right">
          <a class="fanju-new" href="javascript:;">
            新番时间表
            <i class="blbl-icon fanju-new-icon"></i>
          </a>
        </div>
      </module-tab>
      <fanju-list :fanjuList="currentList" />
    </div>
    <div class="module-right">
      <ranking :show="false" />
    </div>
  </div>
</template>
<script>
import moduleTab from "../common/moduleTab";
import ranking from "../common/vedioRanking";
import tabBar from "./child/tabbar";
import fanjuList from "./child/fanjuList";

export default {
  props: {
    fanjuType: {
      type: Number,
      default() {
        return 0;
      }
    }
  },
  data() {
    return {
      fullList: [],
      currentList: []
    };
  },
  methods: {
    changeTime(i) {
      // console.log(i)
      // this.currentList = this.fullList[i]
    }
  },
  computed: {
    title() {
      if (this.fanjuType == 0) return "番剧";
      else return "国创";
    }
  },
  components: {
    moduleTab,
    tabBar,
    fanjuList,
    ranking
  }
};
</script>
<style scoped>
.log-fj {
  background-position: -141px -140px;
}
.log-gc {
  background-position: -140px -1611px;
}
.fanju-new {
  display: block;
  text-decoration: none;
  padding: 0 15px;
  height: 34px;
  line-height: 34px;
  font-size: 14px;
  border-radius: 4px;
  border: 1px solid #f25d8e;
  color: #f25d8e;
  transition: all 0.1s ease;
}
.fanju-new:hover {
  background: #f25d8e;
  color: #fff !important;
}
.fanju-new-icon {
  display: inline-block;
  vertical-align: middle;
  background-position: -478px -281px;
  width: 6px;
  height: 12px;
}
.fanju-new:hover .fanju-new-icon {
  background-position: -541px -218px;
}
</style>
