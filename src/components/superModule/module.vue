<template>
  <div class="module-container">
    <div class="module-left">
      <module-tab>
        <div slot="tab_left">
          <i v-if="showLog" :class="['blbl-icon','module-log',logType]"></i>
          <a href="javascript:;" :class="['module-name', showLog ? '' : 'small-name']">{{ moduleName }}</a>
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
        <div slot="tab_right">
          <more />
        </div>
      </module-tab>
      <ul class="module-left-main" key="1">
        <vedio :watchLater="watchLater" v-for="i in 10" :key="i" />
      </ul>
    </div>
    <div class="module-right">
      <ranking v-if="isRanking" />
      <div v-else>
        <div class="fanju-news-right-top">
          <span class="special">特别推荐</span>
        </div>
        <div class="fanju-news-slider">
          <div class="slide-content" :style="'left:-'+slideLeft+'%'">
            <a v-for="(i,index) in 3" :key="index" class="slide-item" href="javascript:;" :style="'background:url('+slideImgs[index]+') no-repeat center/cover;'">
              <!-- <img :src="slideImgs[index]" alt /> -->
            </a>
          </div>
          <div class="slide-details">
            <p class="current-slide-title">文字说明</p>
            <div class="slide-controller">
              <span @mouseover="goSlide(0)" :class="{'normal-slide':1,'current-slide':slide == 0}"></span>
              <span @mouseover="goSlide(1)" :class="{'normal-slide':1,'current-slide':slide == 1}"></span>
              <span @mouseover="goSlide(2)" :class="{'normal-slide':1,'current-slide':slide == 2}"></span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import moduleTab from "../common/moduleTab";
import more from "../common/moduleMore";
import vedio from "../common/video";
import ranking from "../common/vedioRanking";

export default {
  props: {
    moduleName: {
      type: String,
      default() {
        return "";
      }
    },
    moduleType:{
        type:Number,
        default(){
            return -1
        }
    },
    showLog: {
      type: Boolean,
      default() {
        return true;
      }
    },
    isRanking: {
      type: Boolean,
      default() {
        return true;
      }
    },
    watchLater: {
      type: Boolean,
      default() {
        return true;
      }
    }
  },
  data() {
    return {
      selectedIndex: 1,
      slideImgs: [
        "https://pic.netbian.com/uploads/allimg/201110/234958-1605023398e2c3.jpg",
        "https://pic.netbian.com/uploads/allimg/210308/230659-161521601970be.jpg",
        "https://pic.netbian.com/uploads/allimg/200405/171302-1586077982d6cd.jpg"
      ],
      slide: 0
    };
  },
  methods: {
    changeIndex(i) {
      this.selectedIndex = i;
    },
    goSlide(i) {
      this.slide = i;
    }
  },
  computed: {
    slideLeft() {
      return this.slide * 100;
    },
    logType() {
      switch (this.moduleType) {
        case 0:
          return "log-cartoon";
        case 1:
          return "log-music";
        case 2:
          return "log-dance";
        case 3:
          return "log-game";
        case 4:
          return "log-science";
        case 5:
          return "log-digital";
        case 6:
          return "log-life";
        case 7:
          return "log-guichu";
        case 8:
          return "log-fashion";
        case 9:
          return "log-ad";
        case 10:
          return "log-entertainment";
        case 11:
          return "log-movie";
        case 12:
          return "log-tv";
        case 13:
          return "log-mvAtv";
        case 14:
          return "log-documentary";
        default:
            return 'unknown'
      }
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
/* log */
.log-cartoon {
  background-position: -141px -908px;
}
.log-music{
    background-position: -140px -266px;
}
.log-dance{
    background-position: -141px -461px;
}
.log-game{
background-position: -141px -203px;
}
.log-science{
    background-position: -141px -525px;
}
.log-digital{
    background-position: -140px -1741px;
}
.log-life{
    background-position: -137px -970px;
}
.log-guichu{
    background-position: -141px -332px;
}
.log-fashion{
    background-position: -141px -718px;
}
.log-ad{
    background-position: -140px -1228px;
}
.log-entertainment{
    background-position: -141px -1032px;
}
.log-movie{
    background-position: -141px -396px;
}
.log-tv{
background-position: -141px -845px;
}
.log-mvAtv{
background-position: -141px -845px;
}
.log-documentary{
    background-position: -141px -845px;
}
.fanju-news-right-top {
  height: 45px;
}
.special {
  font-size: 18px;
  font-weight: 400;
}
.fanju-news-slider {
  position: relative;
  height: 268px;
  width: 260px;
  overflow: hidden;
  border-radius: 4px;
}
.slide-content {
  position: relative;
  height: 100%;
  width: 100%;
  display: flex;
  transition: all 0.3s;
}
.slide-item {
  display: inline-block;
  height: 100%;
  width: 100%;
  flex-shrink: 0;
}
.slide-item img {
  height: 100%;
  width: 100%;
}
.slide-details {
  position: absolute;
  bottom: 0;
  width: 100%;
  height: 35px;
  line-height: 35px;
  box-sizing: border-box;
  padding: 0 10px;
  background: linear-gradient(transparent, rgba(0, 0, 0, 0.5));
}
.current-slide-title {
  display: inline-block;
}
.slide-controller {
  /* display: inline-block; */
  float: right;
}
.normal-slide {
  display: inline-block;
  margin: 0 5px;
  width: 9px;
  height: 6px;
  background-color: #fff;
  border-radius: 10px;
  cursor: pointer;
  transition: all 0.3s;
}
.current-slide {
  width: 30px;
  background-color: #f45d8f;
}
</style>

