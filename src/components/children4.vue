<!-- @format -->

<template>
  <div>
    <div class="title">
      <hr />
      <h2>{{ title }}</h2>
      <div class="msg">驾考宝典整合学车全流程，驾考宝典为用户提供全方位学车服务</div>
    </div>

    <ul class="main">
      <li v-for="item in 6" :key="item">
        <a href="javascript:">
            <p>找驾校</p>
        </a>
        <span>口碑好的驾校</span>
      </li>
    </ul>
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

.main{
    width: 1200px;
    height: 372px;
    margin: 0 auto;
    display: flex;
    justify-content: space-between;
    text-align: center;

    a{
        display: block;
        width: 120px;
        height: 120px;
        border-radius: 50%;
        background: url(../assets/icon10.png) no-repeat center;
        padding-top: 120px;
        &:hover{
            background-color: #37b5f8;
        }
    }

    p {
        margin-top: 20px;
        font-size: 24px;
        color: #333;
    }
    span {
        display: block;
        margin-top: 60px;
    }
    
}
</style>
