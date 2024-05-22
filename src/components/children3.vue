<!-- @format -->

<template>
    <div>
      <div class="title">
        <hr />
        <h2>{{ title }}</h2>
      </div>
      
      <ul class="box">
        <li class="item" v-for="item in 4" :key="item">
            <div class="top">
                <div class="left">
                    <span>长安驾校</span>
                    <img src="https://hefei.jiakaobaodian.com/core-assets/jiakao/application/home/files/26170a2c1308047cbc25d47cc860cd1e.png" alt="">
                    <br>
                    <i v-for="item in 4" :key="item">推荐</i>
                </div>
                <div class="right">
                    <i>￥2686</i>
                    <button>学车报名</button>
                </div>
            </div>
            <div class="bottom">
                <img src="https://avatar-user.mucang.cn/user-avatar/default/gV3e8ad1W8E.jpg!100x100" alt="" style="width: 40px;">
                教练非常好，耐心教
            </div>
        </li>
      </ul>

      <button class="btn">查看更多</button>
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
  }

  .box {
    width: 1200px;
    margin: 0 auto;
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;
    li {
        width: 582px;
        height: 254px;
        padding: 40px 30px;
        margin-bottom: 40px;
        outline: 1px solid #000;

        .top {
            .left {
                float: left;
                padding-right: 10px;
                border-right: 1px solid #000;
                span {
                    margin-right: 15px;
                }
                i {
                    font-style: normal;
                    display: inline-block;
                    padding-left: 20px;
                    background: url(https://hefei.jiakaobaodian.com/core-assets/jiakao/application/home/files/24bc3d8a827f32b86d0ed191681125f9.png) no-repeat left center;
                    margin-right: 15px;
                }
            }
            .right {
                display: flex;
                justify-content: space-around;
                align-items: center;
                i {
                    font-style: normal;
                    font-size: 30px;
                    color: red;
                }
                button {
                    width: 80px;
                    height: 30%;
                }
            }
        }
        .bottom {
            display: flex;
            align-items: center;
            padding-left: 20px;
            width: 520px;
            height: 80px;
            margin-top: 40px;
            background-color: #FAFAFA;
        }
    }
  }

  .btn{
    display: block;
    width: 280px;
    height: 50px;
    margin: 0 auto;
    background-color: #fff;
    border: 1px solid #ccc;
    border-radius: 5px;
    &:hover {
        background-color: #56c0f1;
    }
    
  }


  </style>
  