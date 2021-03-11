<template>
  <li class="item-container">
    <a class="cover">
      <img :src="post.cover" alt="" />
    </a>
    <div class="item-info">
      <a href="javascript:;" class="info-title"
        >标题标题标题标题标题标题标题标题标题标题标题标题标题标题标题标题</a
      >
      <div class="info-view">
        <div>
          <i class="blbl-icon info-log view-log"></i>
          <span>20.0万</span>
        </div>
        <div>
          <i class="blbl-icon info-log comment-log"></i>
          <span>999</span>
        </div>
        <div>up</div>
      </div>
    </div>
  </li>
</template>
<script>
export default {
  props: {
    post: {
      type: Object,
      default() {
        return {};
      },
    },
  },
};
</script>
<style scoped>
.item-container {
  width: 420px;
  height: 75px;
  margin: 5px 0;
  display: flex;
}
.cover {
  flex-shrink: 0;
  width: 100px;
  height: 75px;
  border-radius: 4px;
  overflow: hidden;
}
.cover img {
  height: 100%;
  width: 100%;
}
.item-info {
  width: 305px;
  margin-left: 15px;
}
.info-title {
  display: block;
  line-height: 20px;
  width: 100%;
  height: 40px;
  overflow: hidden;
  white-space: nowrap;
  text-overflow: ellipsis;
  text-decoration: none;
  color: #222;
  transition: all 0.3s ease;
}
.info-title:hover {
  color: #00a1d6;
}
.info-view {
  margin-top: 10px;
  display: flex;
}
.info-view div {
  flex: 1;
  color: #99a2aa;
}
.info-log {
  display: inline-block;
  vertical-align: -1px;
  width: 14px;
  height: 12px;
  margin-right: 4px;
}
.view-log {
  background-position: -345px -218px;
}
.comment-log {
  background-position: -345px -281px;
}
</style>
