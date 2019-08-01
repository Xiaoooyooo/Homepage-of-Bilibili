<template>
  <div class="header-container">
    <div class="content">
      <app-nav />
      <div class="head-body">
        <div class="search">
          <a href="javascript:;" class="ranking">
            <span class='blbl-icon'>排行榜</span>
          </a>
          <form action="#" method="GET">
            <input class="input-search" placeholder="Xxxxxxxx" name="keyword" type="text" />
            <!-- 禁用submit -->
            <button class="blbl-icon btn-search" type="button"></button>
          </form>
        </div>
        <a class="blbl-log" href="javascript:;"></a>
      </div>
    </div>
    <main-nav />
  </div>
</template>
<script>
import appNav from './children/appnav'
import mainNav from './children/mainnav'
export default {
  data() {
    return {
    };
  },
  
  components:{
    appNav,
    mainNav
  }
};
</script>
<style scoped>

.header-container {
  height: 230px;
  width: 100%;
}
.content {
  position: relative;
  height: 170px;
  width: 100%;
  background: url("https://i0.hdslb.com/bfs/archive/3329c9f0abfb925ae30441f24d924ad3c19775df.png")
    no-repeat 50% 0;
}

/* .profile-pic:hover{
    transform: translateY(21px) scale(1.5);
} */

.blbl-log {
  position: absolute;
  display: block;
  left: 24px;
  height: 105px;
  width: 220px;
  background: url("https://i0.hdslb.com/bfs/archive/6592e92861e6248205af17702d06ea3f97d81de6.png")
    no-repeat 0 0;
}
.head-body {
  position: relative;
  width: 1160px;
  min-width: 980px;
  margin: 0 auto;
  height: 128px;
}
.search {
  position: absolute;
  right: 0;
  bottom: 20px;
  background: rgba(255, 255, 255, 0.2);
  display: flex;
  align-items: center;
  justify-content: center;
}
.ranking {
  margin-right: 3px;
  font-size: 12px;
  line-height: 32px;
  background: rgba(255, 255, 255, 0.88);
  border-radius: 4px;
  text-decoration: none;
  color: #f25d8e;
}
.ranking > span {
  display: block;
  padding-left: 26px;
  padding-right: 5px;
  background-position: -659px -655px;
}
.input-search {
  width: 200px;
  line-height: 32px;
  outline: none;
  border: none;
  padding: 0 8px;
  border-radius: 4px;
  background: rgba(255, 255, 255, 0.88);
}
.btn-search {
  position: absolute;
  cursor: pointer;
  right: 0;
  height: 100%;
  width: 42px;
  border: none;
  outline: none;
  background-position: -653px -720px;
}
.btn-search:hover {
  background-position: -718px -720px;
}
</style>
