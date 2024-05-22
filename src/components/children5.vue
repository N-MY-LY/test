<!-- @format -->

<template>
  <div>
    <div class="title">
      <hr />
      <h2>{{ title }}</h2>
      <div class="msg">强大的驾考功能，优秀的用户体验，我们的愿景是学车无忧，轻松拿本</div>
    </div>

    <div class="box">
      <img
        src="../assets/home-dynamic.png"
        alt="" />
    </div>
  </div>
</template>

<script>
import item from './item.vue';
export default {
  name: 'children5',
  components: {
    item
  },
  props: ['title']
};
</script>

<style lang="less" scoped>
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

  .msg {
    text-align: center;
    margin-top: 50px;
    color: #1a1818;
  }
}

.box {
  width: 1200px;
  height: 211px;
  margin: 0 auto;
  
}
</style>
