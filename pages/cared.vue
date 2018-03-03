<template>
    <div>
        <my-header></my-header>
        <div class="main">
            <div class="aside">
                <div class="h">
                    <div class="all">
                        <a href="javascript:;">
                            全部关注<i class="fa fa-chevron-circle-down " @click="alldownshow=!alldownshow"></i>
                        </a>
                        <ul class="all-down" v-if="alldownshow">
                            <li>
                                <a href="javascript:;">
                                    全部关注</i>
                                </a>
                            </li>
                            <li>
                                <a href="javascript:;">
                                    只看作者</i>
                                </a>
                            </li>
                            <li>
                                <a href="javascript:;">
                                    只看文集</i>
                                </a>
                            </li>
                            <li>
                                <a href="javascript:;">
                                    只看专题</i>
                                </a>
                            </li>
                            <li>
                                <a href="javascript:;">
                                    只看推送更新</i>
                                </a>
                            </li>
                        </ul>
                    </div>
                    <div class="add">
                        <nuxt-link to="/cared/addcared">
                            <i class="fa fa-user"></i>添加关注
                        </nuxt-link>
                    </div>
                </div>
                <ul class="lists">
                    <li :class="{isActive:this.$route.path=='/cared/qyq'}">
                        <nuxt-link to="/cared/qyq">
                            <img class="yuan" src="../assets/img/default-avatar.jpg" alt="">
                            简友圈
                        </nuxt-link>
                    </li>
                    <li :class="{isActive:this.$route.path=='/cared/dushu'}">
                        <nuxt-link to="/cared/dushu">
                            <img class="fang" src="../assets/img/default-avatar.jpg" alt="">
                            读书
                        </nuxt-link>
                    </li>
                    <li >
                            <nuxt-link to="/">
                                <img class="fang" src="../assets/img/default-avatar.jpg" alt="">
                                读书
                            </nuxt-link>
                        </li>
                        <li :class="">
                                <nuxt-link to="/">
                                    <img class="fang" src="../assets/img/default-avatar.jpg" alt="">
                                    读书
                                </nuxt-link>
                            </li>
                            <li :class="">
                                    <nuxt-link to="/">
                                        <img class="fang" src="../assets/img/default-avatar.jpg" alt="">
                                        读书
                                    </nuxt-link>
                                </li>
                                <li :class="">
                                        <nuxt-link to="/">
                                            <img class="fang" src="../assets/img/default-avatar.jpg" alt="">
                                            读书
                                        </nuxt-link>
                                    </li>
                                    <li :class="">
                                            <nuxt-link to="/">
                                                <img class="fang" src="../assets/img/default-avatar.jpg" alt="">
                                                读书
                                            </nuxt-link>
                                        </li>
                                        <li :class="">
                                                <nuxt-link to="/">
                                                    <img class="fang" src="../assets/img/default-avatar.jpg" alt="">
                                                    读书
                                                </nuxt-link>
                                            </li>
                                            <li :class="">
                                                    <nuxt-link to="/">
                                                        <img class="fang" src="../assets/img/default-avatar.jpg" alt="">
                                                        读书
                                                    </nuxt-link>
                                                </li>
                </ul>
            </div>
            <nuxt-child></nuxt-child>
        </div>
    </div>
</template>
<script>
    import myHeader from '../components/myHeader.vue'
    export default {
        name:'cared',
        components:{
            myHeader
        },
        data () {
            return {
                alldownshow:false,
            }
        }
    }
</script>
<style scoped>
 @media (min-width:992px){
    .main {
        width: 960px;
    }
    .aside{
        width: 260px;
    }
    
}

@media (max-width:1080px){
    .main {
        width: 750px;
    }
    .aside{
        width: 200px;
    }
}   
.main{
    margin: 30px auto;
    position: relative;
}
.aside{
    float: left;
    height: 585px;
    overflow: scroll;
    overflow-x: hidden;
    position: fixed;
    bottom: 0;
}
.aside .h{
    border-bottom: 1px solid #eaeaea;
    height: 20px;
    padding-bottom: 30px;
}
.aside .h .all{
    margin-left: 15px;
    font-size: 15px;
    float: left;
    position: relative;
}
.aside .h .all i{
    color: #969696;
    margin-left: 5px;
}
.aside .h .all ul{
    text-align: center;
    width: 130px;
    position: absolute;
    top: 30px;
    right: -55px;
    background-color: #fff;
    z-index: 1000;
    border: 1px solid #eaeaea;
    box-shadow: 0 2px 8px rgba(0,0,0,.1);
    padding: 5px 0;
}
.aside .h .all ul li{
    line-height: 30px;
}
.aside .h .all ul li a{
    display: block;
    padding: 10px 20px;
    clear: both;
    font-weight: 400;
    line-height: 1.42857;
    color: #333;
    white-space: nowrap;
}
.aside .h .all ul li:hover{
    background-color: #f5f5f5;
}
.aside .h .all ul:after,.aside .h .all ul:before {
    position: absolute;
    top: -10px;
    left: 45%;
    content: "";
    display: inline-block;
    border-left: 9px solid transparent;
    border-right: 9px solid transparent;
    border-bottom: 9px solid transparent
}

.aside .h .all ul:after {
    top: -9px;
    border-bottom: 9px solid #fff
}

.aside .h .add{
    margin-top: 2px;
    float: right;
    font-size: 13px;
}
.aside .h .add i{
    margin-right: 5px;
}
.aside .lists {
    clear: both;
}
.aside .lists a{
    height: auto;
    padding: 10px 15px;
    line-height: 30px;
    display: block;
}
.aside .lists li{
    border-radius: 4px;
    font-size: 14px;
}
.aside .lists li .yuan{
    width: 40px;
    height: 40px;
    border-radius: 50%;
    margin-right: 5px;
}
.aside .lists li .fang{
    width: 40px;
    height: 40px;
    border-radius: 5px;
    margin-right: 5px;
}
.aside .lists li:hover{
    background-color: #f0f0f0;
}
nuxt-child{
    float: right;
}
.isActive{
    background-color: #f0f0f0;
}   
</style>