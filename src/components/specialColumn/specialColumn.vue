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
        <item v-for='post of posts' :post='post' :key='post.key' />
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
  data() {
    return {
      //暂用同样的数据表示
      posts: [{
        key: '002',
        cover: 'https://pic.netbian.com/uploads/allimg/201207/181311-16073359918b8b.jpg',
        info: 'some text.....'
      },{
        key: '003',
        cover: 'https://pic.netbian.com/uploads/allimg/201207/181311-16073359918b8b.jpg',
        info: 'some text.....'
      },{
        key: '004',
        cover: 'https://pic.netbian.com/uploads/allimg/201207/181311-16073359918b8b.jpg',
        info: 'some text.....'
      },{
        key: '005',
        cover: 'https://pic.netbian.com/uploads/allimg/201207/181311-16073359918b8b.jpg',
        info: 'some text.....'
      },{
        key: '006',
        cover: 'https://pic.netbian.com/uploads/allimg/201207/181311-16073359918b8b.jpg',
        info: 'some text.....'
      },{
        key: '007',
        cover: 'https://pic.netbian.com/uploads/allimg/201207/181311-16073359918b8b.jpg',
        info: 'some text.....'
      },{
        key: '008',
        cover: 'https://pic.netbian.com/uploads/allimg/201207/181311-16073359918b8b.jpg',
        info: 'some text.....'
      },{
        key: '001',
        cover: 'https://pic.netbian.com/uploads/allimg/201207/181311-16073359918b8b.jpg',
        info: 'some text.....'
      }]
    }
  },
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
