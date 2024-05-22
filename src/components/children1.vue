<template>
    <div>
        <div class="title">
            <hr>
            <h2>{{ title }}</h2>
        </div>

        <main>
            <div class="left">
                    <div class="top">
                      
                        <a href="javascript:">
                            <img src="../assets/icon5.png" alt="">
                            科目一交规
                        </a>
                    </div>
                    <ul class="bottom">
                        <li>
                            <img src="../assets/icon6.png" alt="">
                            <div class="box">
                                <p>顺序练习</p>
                                <span>按照顺序练习做题</span>
                            </div>
                        </li>
                        <li>
                            <img src="../assets/icon7.png" alt="">
                            <div class="box">
                                <p>随机练习</p>
                                <span>按随机顺序做题</span>
                            </div>
                        </li>
                        <li>
                            <img src="../assets/icon8.png" alt="">
                            <div class="box">
                                <p>专项练习</p>
                                <span>分门别类重点突破</span>
                            </div>
                        </li>
                        <li>
                            <img src="../assets/icon9.png" alt="">
                            <div class="box">
                                <p>难题攻克</p>
                                <span>准确把握考试难点</span>
                            </div>
                        </li>
                    </ul>
                    <button class="btn">模拟考试</button>
            </div>
            <div class="right">
                    <div class="top">
                      
                        <a href="javascript:">
                            <img src="../assets/icon5.png" alt="">
                            科目四安全文明驾驶
                        </a>
                    </div>
                    <ul class="bottom">
                        <li>
                            <img src="../assets/icon6.png" alt="">
                            <div class="box">
                                <p>顺序练习</p>
                                <span>按照顺序练习做题</span>
                            </div>
                        </li>
                        <li>
                            <img src="../assets/icon7.png" alt="">
                            <div class="box">
                                <p>随机练习</p>
                                <span>按随机顺序做题</span>
                            </div>
                        </li>
                        <li>
                            <img src="../assets/icon8.png" alt="">
                            <div class="box">
                                <p>专项练习</p>
                                <span>分门别类重点突破</span>
                            </div>
                        </li>
                        <li>
                            <img src="../assets/icon9.png" alt="">
                            <div class="box">
                                <p>难题攻克</p>
                                <span>准确把握考试难点</span>
                            </div>
                        </li>
                    </ul>
                    <button class="btn">模拟考试</button>
            </div>
        </main>
    </div>
</template>

<script>
    export default {
        name: "children",
        props: ['title']
    }
</script>

<style lang="less" scoped>
.title {
    position: relative;
    width: 1200px;
    height: 41px;
    margin: 60px auto;

    hr{
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

main {
    width: 1200px;
    height: 372px;
    margin: 0 auto;
    display: flex;
    justify-content: space-between;
    .left,
    .right {
        width: 580px;
        height: 372px;
        outline: 1px solid #b6afaf;
    }

    .top {
        a {
            display: block;
            height: 110px;
            text-align: center;
            line-height: 110px;
            color: black;

            img {
                vertical-align: middle;
                margin-right: 5px;
            }
        }
    }
    .bottom {
        width: 100%;
        display: flex;
        justify-content: space-evenly;
        align-items: center;
        align-content: center;
        text-align: center;
        flex-wrap: wrap;
        margin-top: 0px;
        li {
            width: 250px;
            margin: 15px 0;
            display: flex;
            justify-content: center;
            text-align: left;
            align-items: center;
            background-color: #FAFAFA;
            font-size: 14px;
            img {
                width: 30px;
                height: 30px;
                margin-right: 5px;
            }

            p {
                font-size: 16px;
                color: #333;
            }
        }
    }

    .btn {
        display: block;
        width: 300px;
        height: 46px;
        background-color: #37B5F8;
        color: #fff;
        margin: 0 auto;
        margin-top: 20px;
        border: none;
        border-radius: 5px;
    }
}
</style>