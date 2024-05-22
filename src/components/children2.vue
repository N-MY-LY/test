<!-- @format -->

<template>
  <div>
    <div class="title">
      <hr />
      <h2>{{ title }}</h2>
    </div>
    <p class="msg">口碑人气排行榜，助你轻松找驾校</p>

    <!-- 子组件 -->
    <div class="children">
      <item title="综合排行榜">
        <template v-slot:main>
          <dd class="main">
            <a href="javascript:">
              <img
                src="https://jiaxiaozhijia.mc-cdn.cn/jiaxiaozhijia/2023/02/09/01/4ced4231d79c4eeeba5de648e1c47409.png"
                alt="" />
            </a>
            <div class="right">
              <a href="javascript:">金新驾校</a>
              <p>周新增学员：1811人</p>
              <p>安徽省合肥市蜀山区稻香村街安徽省合肥市蜀山区稻香村街安徽省合肥市蜀山区稻香村街安徽省合肥市蜀山区稻香村街</p>
            </div>
          </dd>
        </template>
      </item>
      <item title="口碑排行榜"></item>
      <item title="教练排行榜"></item>
    </div>
  </div>
</template>

<script>
import item from './item.vue';
export default {
  name: 'children',
  components: {
    item
  },
  props: ['title']
};
</script>

<style lang="less">
.title {
  position: relative;
  width: 1200px;
  height: 41px;
  margin: 60px auto;

  hr {
    margin-top: 20px;
  }

  h2 {
    position: absolute;

    z-index: 10;
    top: 0%;
    left: 50%;
    font-size: 30px;
    font-weight: normal;
    color: #000000;
    transform: translate(-50%, -50%);
    text-align: center;
    background-color: #fff;
    padding: 0 20px;
  }
}
.msg {
  text-align: center;
  margin-top: -50px;
  color: #000000;
}

.children {
  display: flex;
  justify-content: space-between;
  width: 1200px;
  margin: 0 auto;
}

.main {
  display: flex;

  > a {
    display: block;
    width: 100px;
    height: 70px;
    overflow: hidden;
    img {
      width: 100px;
    }
  }

  .right {
    padding-left: 5px;
    a {
      display: block;
      color: #000000;
      font-size: 16px;
      margin: 5px 0;
    }
    p {
      width: 200px;
      height: 16px;
      font-size: 14px;
      white-space: nowrap;
      overflow: hidden;
      text-overflow: ellipsis;
    }
  }
}
</style>
