<template>
  <div class="module-container">
    <div class="module-left">
      <module-tab>
          <div slot="tab_left">
          <i class="blbl-icon module-log log"></i>
          <a href="javascript:;" class="module-name">专栏</a>
          </div>
        <div slot="tab_right">
          <more msg='换一换' />
        </div>
      </module-tab>
      <ul class="module-left-main" key="1">
        <item v-for='(i,index) in 8' :key='index' />
      </ul>
    </div>
    <div class="module-right">
      <ranking />
    </div>
  </div>
</template>
<script>
import moduleTab from "../common/moduleTab";
import more from "../common/moduleMore";
import ranking from "../common/vedioRanking";
import item from './child/item';

export default {
  components: {
    moduleTab,
    more,
    ranking,
    item
  }
};
</script>
<style scoped>
.log{
    background-position: -138px -1803px;
}
</style>
