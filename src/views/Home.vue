<template>
  <div class="home">
    <main-nav></main-nav>
    <!-- 侧边导航 -->
    <div class="side-bar-container">
      <sidebar />
    </div>
    <div class="container">
      <recommend />
      <spread />
      <ad
        imgsrc="https://i0.hdslb.com/bfs/sycp/creative_img/201907/e9c005fb1af07d30c94e7ab1bf3c8ab4.jpg"
      />
      <live />
      <!-- 动画 moduleType = 0 -->
      <module moduleName="动画" :moduleType="0" />
      <ad
        imgsrc="https://i0.hdslb.com/bfs/sycp/creative_img/201907/79420d1aaa5dac288649257d176f81dc.jpg"
      />
      <!-- 番剧 -->
      <fanju />
      <!-- 番剧动态 -->
      <module moduleName="番剧动态" :watchLater="false" :showLog="false" :isRanking="false" />
      <!-- 国创 -->
      <fanju :fanjuType="1" />
      <!-- 国产原创相关 -->
      <module moduleName="国产原创相关" :showLog="false" />
      <!-- 音乐 moduleType = 1 -->
      <module moduleName="音乐" :moduleType="1" />
      <!-- 舞蹈 moduleType = 2 -->
      <module moduleName="舞蹈" :moduleType="2" />
      <!-- 游戏 moduleType = 3 -->
      <module moduleName="游戏" :moduleType="3" />
      <!-- 科技 moduleType = 4 -->
      <module moduleName="科技" :moduleType="4" />
      <!-- 数码 moduleType = 5 -->
      <module moduleName="数码" :moduleType="5" />
      <!-- 生活 moduleType = 6 -->
      <module moduleName="生活" :moduleType="6" />
      <!-- 鬼畜 moduleType = 7 -->
      <module moduleName="鬼畜" :moduleType="7" />
      <!-- 时尚 moduleType = 8 -->
      <module moduleName="时尚" :moduleType="8" />
      <!-- 广告 moduleType = 9 -->
      <module moduleName="广告" :moduleType="9" />
      <!-- 娱乐 moduleType = 10 -->
      <module moduleName="娱乐" :moduleType="10" />
      <!-- 专栏 -->
      <special-column />
      <!-- 电影 -->
      <module moduleName="电影" :moduleType="11" />
      <!-- 电视剧 -->
      <module moduleName="电视剧" :moduleType="12" />
      <!-- 影视 -->
      <module moduleName="影视" :moduleType="13" />
      <!-- 纪录片 -->
      <module moduleName="纪录片" :moduleType="14" />
      <!-- 特别推荐 -->
      <special-recommendation />
      <!-- footer -->
      <end />
    </div>
  </div>
</template>

<script>
import mainNav from "../components/header/header.vue";
import recommend from "../components/recommend/recommend.vue";
import spread from "../components/spread/spread.vue";
import live from "../components/live/live.vue";
import ad from "../components/common/ad";
import fanju from "../components/fanju/fanju";
import module from "../components/superModule/module";
import specialColumn from "../components/specialColumn/specialColumn";
import specialRecommendation from "../components/specialRecommendation/specialRecommendation";
import end from "../components/end/end";
import sidebar from "../components/sidebar/sidebar";

export default {
  data() {
    return {
    };
  },
  name: "home",
  components: {
    mainNav,
    recommend,
    spread,
    live,
    ad,
    fanju,
    module,
    specialColumn,
    specialRecommendation,
    end,
    sidebar
  }
};
</script>
<style scoped>
.container {
  position: relative;
  width: var(--content-width);
  min-width: 960px;
  margin: 0 auto;
}
.side-bar-container {
  position: relative;
  z-index: 9;
  direction: rtl;
  width: var(--content-width);
  height: 0;
  margin: 0 auto;
  top: 230px;
  transition: top 0.3s ease;
}
</style>
