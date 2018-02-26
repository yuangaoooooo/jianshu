<template>
    <div>
        <my-header></my-header>
        <div class="main">
            <div class="aside">
                <div class="h">
                    <div class="all">
                        <nuxt-link to="/">
                            全部关注<i class="fa fa-chevron-circle-down "></i>
                        </nuxt-link>
                    </div>
                    <div class="add">
                        <nuxt-link to="/">
                            <i class="fa fa-user"></i>添加关注
                        </nuxt-link>
                    </div>
                </div>
                <ul>
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
}
.aside .h .all i{
    color: #969696;
    margin-left: 5px;
}
.aside .h .add{
    float: right;
    font-size: 15px;
}
.aside .h .add i{
    margin-right: 5px;
}
.aside ul {
    clear: both;
}
.aside ul a{
    height: auto;
    padding: 10px 15px;
    line-height: 30px;
    display: block;
}
.aside ul li{
    border-radius: 4px;
    font-size: 14px;
}
.aside ul li .yuan{
    width: 40px;
    height: 40px;
    border-radius: 50%;
    margin-right: 5px;
}
.aside ul li .fang{
    width: 40px;
    height: 40px;
    border-radius: 5px;
    margin-right: 5px;
}
.aside ul li:hover{
    background-color: #f0f0f0;
}
nuxt-child{
    float: right;
}
.isActive{
    background-color: #f0f0f0;
}   
</style>