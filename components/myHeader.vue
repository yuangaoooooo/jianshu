<template>
    <div>
        <nav class="navbar navbar-default nav-fixed-top">
            <div class="width-limit">
                <!-- logo -->
                <nuxt-link class="nav-logo" to="/">
                    <img src="../assets/img/nav-logo.png" alt="">
                </nuxt-link>
                <!-- 写文章 -->
                <nuxt-link class="btn write-btn" to="/create">
                    <i class="fa fa-edit"></i>写文章
                </nuxt-link>
                <!-- 登录注册按钮 -->
                <nuxt-link to="/sign-up" class="btn sign-up">注册</nuxt-link>
                <nuxt-link to="/sign-in" class="btn sign-in">登录</nuxt-link>

                <!-- 如果用户登录那么显示用户头像 -->
                <div class="user" style="display:block"  @mouseover="userShow=true" @mouseleave="userShow=false">
                    <div class="drop-down">
                        <nuxt-link class="avatar" to="/user">
                            <img src="../assets/img/default-avatar.jpg" alt="">
                        </nuxt-link>
                    </div>
                    <div class="drop-menu" v-show="userShow">
                        <ul>
                            <li>
                                <nuxt-link to="/me">
                                    <i class="fa fa-home"></i>
                                    我的主页
                                </nuxt-link>
                            </li>
                            <li>
                                <nuxt-link to="/collect">
                                    <i class="fa fa-bookmark"></i>
                                    收藏的文章
                                </nuxt-link>
                            </li>
                            <li>
                                <nuxt-link to="/like">
                                    <i class="fa fa-heart"></i>
                                    喜欢的文章
                                </nuxt-link>
                            </li>
                            <li>
                                <nuxt-link to="/setting/jcsz">
                                    <i class="fa fa-cog"></i>
                                    设置
                                </nuxt-link>
                            </li>
                            <li>
                                <nuxt-link to="/">
                                    <i class="fa fa-sign-out"></i>
                                    退出
                                </nuxt-link>
                                
                            </li>
                        </ul>
                    </div>
                </div>
                <!-- 导航 -->
                <div class="my-container">
                    <ul class="nav-list">
                        <li class="active">
                            <nuxt-link to="/" >
                                <i class="fa fa-compass"></i>
                                <span>发现</span>
                                
                            </nuxt-link>
                        </li>
                        <li>
                            <nuxt-link to="/cared/qyq">
                                <i class="fa fa-book"></i>
                                <span>关注</span>
                                
                            </nuxt-link>
                        </li>
                        <li class="notify" @mouseover="notifyShow=true" @mouseleave="notifyShow=false">
                            <nuxt-link to="/message/pinlun">
                                <i class="fa fa-bell"></i>
                                <span>消息</span>    
                            </nuxt-link>
                            <div class="drop-menu" v-show="notifyShow" @click="isshow">
                                <ul>
                                    <li>
                                        <nuxt-link to="/message/pinlun">
                                            <i class="fa fa-comment-o"></i>
                                            评论
                                        </nuxt-link>
                                    </li>
                                    <li>
                                        <nuxt-link to="/message/jianxin">
                                            <i class="fa fa-envelope-open-o"></i>
                                            简信
                                        </nuxt-link>
                                    </li>
                                    <li>
                                        <nuxt-link to="/message/tougao">
                                            <i class="fa fa-hand-o-up"></i>
                                            投稿请求
                                        </nuxt-link>
                                    </li>
                                    <li>
                                        <nuxt-link to="/message/likezan">
                                            <i class="fa fa-heart-o"></i>
                                            西黄和赞
                                        </nuxt-link>
                                    </li>
                                    <li>
                                        <nuxt-link to="/message/guanzhu">
                                            <i class="fa fa-user-o"></i>
                                            关注
                                        </nuxt-link>
                                    </li>
                                </ul>
                            </div>
                        </li>
                        <!-- 搜索框 -->
                        <li class="search">
                            <form action="" method="post">
                                <input type="text" placeholder="搜索" @focus="bgShow=true" @blur="bgShow=false">
                                <nuxt-link to="/search" class="search-btn" :class="{active:bgShow}">
                                    <i class="fa fa-search" ></i>
                                </nuxt-link>
                            </form>
                        </li>
                    </ul>
                </div>
            </div>
        </nav>
    </div>
</template>
<script>
    export default {
        name:'myHeader',
        data () {
            return {
                userShow:false,
                notifyShow:false,
                bgShow:false,
            }
        },
        methods:{
            isshow:function(){
                this.notifyShow=false;
            }
        }
    }
</script>
<style scoped>
    nav{
        width: 100%;
        height: 56px;
    }
    .navbar{
        padding: 0;
        border-bottom: 1px solid #e7e7e7;
        margin-bottom: 20px;
        background-color: #fff;
    }
    .nav-fixed-top{
        position: fixed;
        top: 0;
        left: 0;
        z-index: 9999;

    }
    nav .width-limit{
        min-width: 768px;
        width: 1440px;
        margin: 0 auto;
    }
    nav .nav-logo{
        float: left;
        height: 56px;
        padding: 0;
    }
    nav .nav-logo img{
        height: 100%;
    }
    nav .write-btn{
        float: right;
        width: 100px;
        height: 40px;
        margin:7px 15px 0;
        line-height: 24px;
        font-size: 16px;
        background: #ea6f5a;
        color: #fff !important;
        border-radius: 20px;
    }
    nav a.sign-in,nav a.sign-up{
        float: right;
        width: 100px;
        height: 40px;
        line-height: 24px;
        font-size: 15px;
    }
    nav a.sign-in{
        margin: 8px 0;
        color: #969696 !important;
    }
    nav a.sign-in:active{
        box-shadow: none;
    }
    nav a.sign-up{
        margin: 8px 6px 0;
        border: 1px solid #ea6f5a;
        border-radius: 20px;
        color: #ea6f5a !important;
    }
    nav a.sign-up:hover{
        background: #fef7f5;
    }
    nav .user{
        float: right;
        position: relative;
    }
    nav .user .avatar{
        position: relative;
        width: 40px;
        height: 40px;
        display: block;
        margin: 8px 28px 8px 20px;
    }
    nav .user:hover{
        background: #f5f5f5;
    }
    nav .user .avatar::before{
        content: "";
        position: absolute;
        top: 18px;
        right: -14px;
        border-left: 5px solid transparent;
        border-right: 5px solid transparent;
        border-top: 6px solid #999;
    }
    nav .user .avatar img {
        width: 100%;
        height: 100%;
        border: 1px solid #ccc;
        border-radius: 50%;
    }
    nav .user .drop-menu{
        position: absolute;
        left: 0;
        min-width: 160px;
        box-shadow: 0 0 8px rgba(0,0,0,.1);
        font-size: 15px;
        background: #fff;
    }
    nav .user .drop-menu ul{
        padding: 10px 0;
        margin: 0;
    }
    nav .user .drop-menu ul li a{
        padding: 10px 20px;
        display: block;
    }
    nav .user .drop-menu ul li a:hover{
        background: #f5f5f5;
    }
    nav .user .drop-menu ul li i{
        margin-right: 15px;
        color: #ea6f5a;
        font-size: 18px;
    }
    nav .nav-list{
        /* overflow: hidden;
        zoom: 1; */
        padding: 0;
        margin: 0 -15px;

    }
    nav .nav-list::after{
        content: '';
        height: 0;
        display: block;
        visibility: hidden;
        clear: both;
    }
    nav .nav-list>li{
        float: left;
        margin-right: 5px;
    }
    nav .nav-list>li:hover{
        background: #f5f5f5;
    }
    nav .nav-list>li>a{
        display: block;
        height: 55px;
        padding: 15px;
        padding-right: 10px;
        font-size: 16px;
    }
    nav .nav-list>li>a>i{
        margin-right: 5px;
        margin-top: 2px;
        font-size: 22px;
        text-align: center;
    }
    nav .nav-list>li.active{
        color: #ea6f5a;
        background: #fff;
    }

    nav .nav-list .search{    
        padding-left:15px; 
    }
    
    nav .nav-list .search:hover{
        background-color: #fff;
    }
    nav .nav-list .search form{
        margin-top: 8.5px;
        position: relative;
    }
    nav .nav-list .search form input{
        width: 240px;
        height: 38px;
        border: none;
        background-color: #eeeeee;
        border-radius: 20px;
        padding: 0 30px 0 20px;
        font-size: 15px;
        transition:width ease-in 0.3s;
    }
    nav .nav-list .search form input:focus{
        width: 320px;
    }
    nav .nav-list .search form a.search-btn{     
        position: absolute;
        top: 4px;
        right: 5px;
        display: block;
        width: 30px;
        height: 30px;
        text-align: center;
        line-height: 30px;
    }
    nav .nav-list .search form a.active{
        background: #969696;
        border-radius: 50%;
        color: #fff !important;
    }
    nav .nav-list .search form a.search-btn i{
        font-size: 18px;
    }
  
    nav .nav-list .notify{
        position: relative;
        
    }
    nav .nav-list .notify .drop-menu{
        position: absolute;
        left: 0;
        min-width: 160px;
        box-shadow: 0 0 8px rgba(0,0,0,.1);
        font-size: 15px;
        background: #fff;
    }
    nav .notify .drop-menu ul{
        padding: 10px 0;
        margin: 0;
    }
    nav .notify .drop-menu ul li a{
        padding: 10px 20px;
        display: block;
    }
    nav .notify .drop-menu ul li a:hover{
        background: #f5f5f5;
    }
    nav .notify .drop-menu ul li i{
        margin-right: 15px;
        color: #ea6f5a;
        font-size: 18px;
    }


    @media (max-width:870px){
        nav .nav-list{
            display: none;
        }
    }
    
    @media (max-width:1360px){
        nav .nav-list>li>a i{
            display: none;
        }
        nav .nav-list .search form input{
            width: 160px;
        }
        nav .nav-list .search form input:focus{
            width: 240px;
        }
    }
    @media (max-width:1080px) {
        nav .nav-list>li>a i{
            display: block;
        }
        nav .nav-list>li>a span{
            display: none;
        }
        nav .nav-list .search form input{
            width: 150px;
        }
        nav .nav-list .search form input:focus{
            width: 150px;
        }
    }
</style>
