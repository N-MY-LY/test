<!-- @format -->

<template>
  <div>
    <!-- 顶部导航 -->
    <div
      id="top"
      class="nat_top">
      <div class="box">
        <ul class="left">
          <li>
            <span class="dw"></span>
            <a
              href="javascript:"
              class="active"
              style="margin-right: 10px"
              >全国</a
            >
            <a href="javascript:">[切换]</a>
          </li>
          <li>|</li>
          <li>
            <a
              href="javascript:"
              style="margin-right: 10px"
              >题库:</a
            >
            <a
              href="javascript:"
              class="active">
              小车</a
            >
          </li>
        </ul>
        <ul class="right">
          <li>
            <a
              href="javascript:"
              class="active"
              >驾校入驻</a
            >
          </li>
          <li>
            <a
              href="javascript:"
              class="active"
              >驾校后台</a
            >
          </li>
          <li>
            <a href="javascript:">登录</a>
          </li>
        </ul>
      </div>
    </div>

    <!-- 中间logo搜索区 -->
    <div class="logo_search w">
      <img
        src="./assets/logo.png"
        alt="" />

      <div class="search_box">
        <input
          type="search"
          name=""
          id=""
          placeholder="请输入关键字" />
        <input
          type="submit"
          value="搜索" />
      </div>
    </div>

    <!-- 底部导航条 -->
    <div class="nav_bottom">
      <ul class="box w">
        <li
          v-for="item in nav_contet"
          :key="item.name"
          :class="{ has_arrow: item.children }"
          @mouseenter="item.ishow = true"
          @mouseleave="item.ishow = false">
          <a href="javascript:">{{ item.name }}</a>
          <ul
            class="dialog"
            v-if="item.children"
            v-show="item.ishow">
            <li
              v-for="(child, index) in item.children"
              :key="index"
              ><a href="javascript:">{{ child }}</a></li
            >
          </ul>
        </li>

        <!-- 悬浮框 -->
        <dl class="menu">
          <dt>学车流程</dt>
          <dd
            v-for="(item, index) in banner_menu"
            :key="index">
            <img
              :src="require('./assets/icon' + (index + 1) + '.png')"
              alt="" />
            <div class="right">
              <p class="p1">{{ item.p1 }}</p>
              <p class="p2">{{ item.p2 }}</p>
            </div>
          </dd>
        </dl>
      </ul>
    </div>

    <!-- 轮播图 -->
    <div class="banner">
      <el-carousel
        trigger="click"
        height="380px">
        <el-carousel-item
          v-for="item in 4"
          :key="item">
          <img
            :src="require('./assets/banner' + item + '.png')"
            alt="" />
        </el-carousel-item>
      </el-carousel>
    </div>

    <!-- 粘性盒子 -->
    <div class="sticky_box">
      <img
        src="./assets//二维码.png"
        alt="" />
      <a
        href="javascript:"
        class="weixin_a"
        @mouseenter="enter(1)"
        @mouseleave="leave"></a>
      <a
        href="javascript:"
        class="weibo_a"
        @mouseenter="enter(2)"
        @mouseleave="leave"></a>
      <a
        class="normal"
        href="javascript:"
        @mouseenter="enter(3)"
        @mouseleave="leave"
        >意见反馈</a
      >
      <a
        class="normal"
        href="#top"
        >返回顶点</a
      >
      <div class="hidden_ele">
        <img
          class="hidden_img"
          src=""
          alt="" />

        <ul
          @mouseleave="leave"
          @mouseenter="enter(3)">
          <li><h4>用户反馈</h4>400-056-1617（电话）</li>
          <li><h4>教练反馈</h4>jiaolian_service@mucang.cn(邮箱)</li>
          <li><h4>驾校反馈</h4>jiaxiao_service@mucang.cn(邮箱)</li>
          <li><h4>学员反馈</h4>点击提交学员反馈</li>
        </ul>
      </div>
    </div>

    <!-- 子组件 -->
    <children1 title="合肥市2024小车理论考试"> </children1>
    <div style="width: 1200px; height: 120px; margin: 30px auto">
      <img
        src="	https://hefei.jiakaobaodian.com/core-assets/static/images/common/banner-jxb.png"
        alt="" />
    </div>
    <children3 title="合肥市驾校推荐"> </children3>
    <children4 title="学车流程"> </children4>
    <children5 title="宝典荣誉"> </children5>

    <!-- 通栏 -->
    <div class="footer">
      <div class="w footer_box">
        <div
          v-for="item in 3"
          :key="item"
          class="ds1 element">
          <span>教练宝典APP</span>
        </div>
      </div>
    </div>

    <!-- 其他信息 -->
    <div class="footer_msg">
      <div class="w footer_msg_box">
        <div class="left">
          <div class="left">
            <p>驾考宝典APP下载</p>
            <span>考驾照 用宝典</span>
          </div>
          <img
            src="./assets/1.png"
            alt="" />
        </div>
        <div class="right">
          <div class="left">
            <p>驾考宝典APP下载</p>
            <span>考驾照 用宝典</span>
          </div>
          <img
            src="./assets/2.jpg"
            alt="" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import children1 from './components/children1.vue';
import children3 from './components/children3.vue';
import children4 from './components/children4.vue';
import children5 from './components/children5.vue';
export default {
  name: 'App',
  components: {
    children1,
    children3,
    children4,
    children5
  },
  data() {
    return {
      nav_contet: [
        { name: '首页' },
        { name: '模拟考试', ishow: false, children: ['科目一', '科目二', '科目三', '科目四'] },
        { name: '找驾校', ishow: false, children: ['找驾校', '找教练', '找陪练'] },
        { name: '驾考圈' },
        { name: '交通标志' },
        { name: '软件下载' },
        { name: '驾考宝典企业版' },
        { name: '智慧驾校' },
        { name: '买新车', ishow: false, children: ['买新车', '买新车', '买新车'] },
        { name: '二手车' }
      ],
      banner_menu: [
        { img: './assets/icon1.png', p1: '科目一', p2: '2024新题库' },
        { img: './assets/icon2.png', p1: '科目二', p2: '精选视频，详解考点' },
        { img: './assets/icon3.png', p1: '科目三', p2: '全方位讲解，攻克难点' },
        { img: './assets/icon4.png', p1: '科目四', p2: '2024新题库' }
      ]
    };
  },
  methods: {
    enter(type) {
      if (type == 1) {
        document.querySelector('.hidden_img').src = require('./assets/微信.png');
      }
      if (type == 2) {
        document.querySelector('.hidden_img').src = require('./assets/微博.png');
      }
      if (type == 3) {
        document.querySelector('.hidden_ele ul').style.display = 'block';
      }
    },
    leave() {
      document.querySelector('.hidden_img').src = '';
      document.querySelector('.hidden_ele ul').style.display = 'none';
    }
  }
};
</script>

<style lang="less">
// 全局样式
* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
  list-style: none;
  text-decoration: none;
  color: #999;
}



.w {
  width: 1200px;
  margin: 0 auto;
}

.nat_top {
  width: 100%;
  height: 34px;
  padding: 7px;
  font-size: 14px;
  background-color: #fafafa;
  .box {
    display: flex;
    justify-content: space-between;
    width: 1200px;
    height: 100%;
    margin: 0 auto;

    .active {
      color: #37b5f8;
    }

    .left {
      display: flex;

      li {
        display: flex;
        align-items: center;
      }

      .dw {
        display: inline-block;
        width: 14px;
        height: 14px;
        margin-right: 3px;
        background: url(./assets/定位.png) no-repeat center center;
        background-size: 100%;
      }

      li:nth-child(2) {
        width: 1px;
        height: 16px;
        line-height: 18px;
        padding: 0 30px;
        color: #dedede;
      }
    }

    .right {
      display: flex;
      justify-content: flex-end;
      li {
        margin-left: 30px;
      }
    }
  }
}

.logo_search {
  height: 98px;
  padding: 28px 0;
  display: flex;
  justify-content: space-between;
  align-items: center;

  img {
    width: 207px;
    height: 42px;
  }

  .search_box {
    display: flex;
    input[type='search'] {
      width: 248px;
      height: 42px;
      padding: 10px;
      vertical-align: top;
      border: 1px solid #ccc;
      &:focus {
        outline: none;
        border-color: #37b5f8;
      }
    }
    input[type='submit'] {
      width: 52px;
      height: 42px;
      color: black;
      background-color: #f0f0f0;
      border: 1px solid #ccc;
      &:focus {
        outline: none;
        border-color: #37b5f8;
      }
    }
  }
}

.nav_bottom {
  width: 100%;
  background-color: #37b5f8;
  .box {
    position: relative;

    height: 50px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    text-align: center;
    li {
      position: relative;
      height: 100%;
      line-height: 50px;
      padding: 0 20px;
      a {
        color: #fff;
      }

      &:hover {
        background-color: #54c0f9;
      }
      &.has_arrow {
        &:after {
          content: '';
          position: absolute;
          top: 45%;
          right: 5%;
          width: 0;
          height: 0;
          border-style: solid;
          border: 5px solid transparent;
          border-top-color: #fff;
        }
      }

      .dialog {
        position: absolute;
        top: 100%;
        left: 0;
        z-index: 1000;
        width: 100%;
        background-color: #736464;
        li {
          height: 40px;
          line-height: 40px;
          padding: 0 20px;
          &:hover {
            color: #37b5f8;
          }
        }
      }
    }

    .menu {
      position: absolute;
      z-index: 10;
      top: 130%;
      left: 0%;
      background-color: #e6f0ff;
      dt {
        height: 70px;
        line-height: 70px;
      }

      dd {
        display: flex;
        align-items: center;
        height: 70px;
        padding: 0 20px;
        &:hover {
          color: #37b5f8;
        }
        img {
          width: 42px;
          margin-right: 15px;
        }

        p {
          text-align: left;
        }

        .p1 {
          font-size: 16px;
          color: #37b5f8;
        }
      }
    }
  }
}

.banner {
  width: 1920px;
  height: 380px;
  margin: 0 auto;

  img {
    width: 100%;
    height: 100%;
  }
}

.sticky_box {
  position: fixed;
  z-index: 20;
  bottom: 100px;
  right: 0;
  width: 117px;
  height: 300px;
  background-color: rgb(255, 255, 255);

  .weixin_a {
    position: absolute;
    top: 158px;
    right: 0;
    width: 108px;
    height: 33px;
    background-color: transparent;
  }
  .weibo_a {
    position: absolute;
    top: 191px;
    right: 0;
    width: 108px;
    height: 33px;
    background-color: transparent;
  }

  .normal {
    position: relative;
    text-align: center;
    top: -4px;
    right: -10px;
    display: block;
    width: 108px;
    height: 33px;
    line-height: 33px;
    outline: 1px solid #f2f2f2;
  }

  .hidden_ele {
    position: absolute;
    top: 158px;
    right: 110px;

    ul {
      position: absolute;
      display: none;
      z-index: 10;
      top: 0px;
      right: -5px;
      width: 148px;
      line-height: 15px;
      outline: 1px solid #f2f2f2;
      font-size: 12px;
      padding: 0 13px;
      li {
        width: 100%;
        border: 1px solid #f2f2f2;
        // 字体换行但是不能隐藏
        word-wrap: break-word;
        word-break: break-all;
        margin: 5px;
        padding: 5px 0;
        border: none;
        border-bottom: 1px solid #f5efef;
        outline: none;
        &:hover {
          background-color: #f2f2f2;
        }
      }
    }
  }
}

.footer {
  width: 100%;
  height: 560px;
  background-color: #f5f5f5;

  .footer_box {
    height: 100%;
    display: flex;
    justify-content: space-between;
    overflow: hidden;

    .ds1 {
      position: relative;
      margin-top: 165px;
      width: 300px;
      height: 500px;
      background: url(./assets/手机信息.png) no-repeat;

      span {
        position: absolute;
        top: -10%;
        left: 50%;
        z-index: 101;
        transform: translate(-50%, 0);
        color: #000000;
        font-size: 24px;
      }

      &:nth-child(2) {
        margin-top: 120px;
        width: 430px;
        height: 540px;
        background: url(./assets/手机信息2.png) no-repeat;
      }
    }
  }
}

@keyframes slideUp {
  0% {
    transform: translateY(0);
  }
  100% {
    transform: translateY(-50px); /* 自下向上移动50px */
  }
}

.element {
  transition: transform 0.5s ease-in-out;
}

.element:hover {
  animation: slideUp 0.5s forwards; /* 播放动画并保持最终状态 */
}

.element:not(:hover) {
  transform: translateY(0); /* 鼠标移出时恢复原样 */
}

.footer_msg {
  width: 100%;
  background-color: #fff;

  .footer_msg_box {
    width: 1200px;
    height: 170px;
    margin: 0 auto;
    display: flex;
    justify-content: space-between;
    >.left,
    >.right {
      width: 600px;
      height: 170px;
      display: flex;
      justify-content: space-around;
      align-items: center;
      img {
        width: 115px;
        height: 115px;
      }
    }

    >.left {
      &::after {
        content: "";
        display: block;
        width: 1px;
        height: 100px;
        background-color: #bbafaf;
      }
    }
  }
}
</style>
