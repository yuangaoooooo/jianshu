<template>
    <div>
        <div class="con" @click.stop="isshow=false;listshow=false">
            <div class="main">
                <div class="one" v-if="oneshow" >
                    <div class="top">
                        全部简信
                    </div>
                    <div class="content-placeholder-guanzhu">
                        <div class="avatar"></div>
                        <div class="title">
                            <div class="name"></div>
                            <div class="jianjie"></div>
                        </div>
                    </div>
                    <div class="user" @click="oneshow=false; twoshow=true">
                        <nuxt-link to="/m/123" class="avatar">
                            <img src="../../assets/img/default-avatar.jpg" alt="">
                        </nuxt-link>
                        <div class="in">
                            <div class="who">贾宝玉 
                                <div class="caozuo">
                                    2017.09.16 06.52
                                    <i class="fa fa-angle-down" @click.stop="isshow=!isshow"></i>
                                </div>
                            </div>
                            <div class="time"> 欢迎加入丰富多彩的原创内容社区——简书。有任何疑问（如何投稿，专题主编，签约作者，简叔，简小...</div>
                        </div>
                        <div class="kuai" v-if="isshow">
                            <ul>
                                <li>
                                    <i class="fa fa-trash-o "></i>
                                    删除会话
                                </li>
                                <li>
                                    <i class="fa fa-frown-o "></i>
                                    加入黑名单
                                </li>
                                <li>
                                    <i class="fa fa-flag-o"></i>
                                    举报用户
                                </li>
                            </ul>
                        </div>
                    </div>
                </div>
                <div class="two" v-if="twoshow">
                    <div class="chat-top">
                        <a href="javascript:;" class="back-to-list" @click="oneshow=true; twoshow=false">
                            <i class="fa fa-reply"></i>返回简信列表
                        </a>
                        <b>与<a href="javascript:;">贾宝玉</a>的对话</b>
                        <div class="">
                            <a href="javascript:;" @click.stop="listshow=true"><i class="fa fa-chevron-down "></i></a>
                            <ul v-if="listshow">
                                <li>
                                    <a href="javascript:;">
                                        <i class="fa fa-frown-o "></i>
                                        加入黑名单
                                    </a>
                                </li>
                                <li>
                                    <a href="javascript:;">
                                        <i class="fa fa-flag-o"></i>
                                        举报用户
                                    </a>
                                </li>
                            </ul>
                        </div>
                    </div>
                    <div class="message-show">
                        <ul class="message-list">
                            <li class="message-l">
                                <a href="javascript:;" class="avatar">
                                    <img src="~/assets/img/default-avatar.jpg" alt="">
                                </a>
                                <div>
                                    <span class="content">
                                        欢迎加入丰富多彩的原创内容社区—简书。新手有关简书的任何疑问请点击链接查看 
                                    </span>
                                </div>
                                <span class="time">02.23 08:30</span>
                            </li>
                            <li class="message-r">
                                <a href="javascript:;" class="avatar">
                                    <img src="~/assets/img/default-avatar.jpg" alt="">
                                </a>
                                <div>
                                    <span class="content">
                                        你好
                                    </span>
                                </div>
                                <span class="time">02.23 08:30</span>
                            </li>
                            <li class="message-l">
                                    <a href="javascript:;" class="avatar">
                                        <img src="~/assets/img/default-avatar.jpg" alt="">
                                    </a>
                                    <div>
                                        <span class="content">
                                            欢迎加入丰富多彩的原创内容社区—简书。新手有关简书的任何疑问请点击链接查看 
                                        </span>
                                    </div>
                                    <span class="time">02.23 08:30</span>
                                </li>
                                
                                
                        </ul>
                    </div>
                    <div class="write-message">
                        <form>
                            <textarea type="text" placeholder="输入内容" class="form-control"></textarea> 
                            <input type="submit" class="btn btn-send" value="发送">
                        </form>
                        <div class="hint">Enter 直接发送</div>
                    </div>
                </div>
            </div>
        </div>
       
    </div>
</template>
<script>
    export default {
        name:'jianxin',
        components:{
            
        },
        data () {
            return {
                isshow:false,
                listshow:false,
                oneshow:true,
                twoshow:false
            }
        },

    }
</script>
<style scoped>
 @media (min-width:992px){
    .con{
        margin-left: 300px;
    }
    
}

@media (max-width:1080px){
    .con{
        margin-left: 240px;
    }
    .in{
        width: 360px;
    }
}  
.con{
    padding: 10px 0 0 5px;
    height: 580px;
}
.con .top{
    padding-bottom: 20px;
    font-size: 14px;
    font-weight: 700;
    border-bottom: 1px solid #eaeaea;
    margin-bottom: 20px;
}
.content-placeholder-guanzhu{
    padding: 10px 0 20px 20px;
}
.content-placeholder-guanzhu .avatar{
    width: 40px;
    height: 40px;
    margin-right: 10px;
    display: inline-block;
    vertical-align: middle;
    background-color: #eaeaea;
    border-radius: 50%;
}
.content-placeholder-guanzhu .title{
    display: inline-block;
    vertical-align: middle;
}
.content-placeholder-guanzhu .title .name{
    width: 60px;
    height: 16px;
    background-color: #eaeaea;
    margin-bottom: 10px;
}
.content-placeholder-guanzhu .title .jianjie{
    width: 230px;
    height: 14px;
    background-color: #eaeaea;
    animation: loading3 1s ease-in-out infinite;
}

@keyframes loading3{
    0%{
        width: 50px;
    }
    25%{
        width: 230px;
    }
    50%{
        width: 230px;
    }
    100%{
        width: 50px;
    }
}
.user{
    padding: 10px 0 20px 20px;
    border-bottom: 1px solid #eaeaea;
    position: relative;
    cursor: pointer;
}
.user .avatar{
    width: 40px;
    height: 40px;
    border-radius: 50%;
    display: inline-block;
    vertical-align: middle;
    margin-right: 10px;
}
.user .in{
    display: inline-block;
    vertical-align: middle;
}
.user .in .who{
    font-size: 15px;
}
.user .in .time{
    font-size: 12px;
    color: #969696;
}
.user .neiron{
    margin: 10px 0;
}
.user .meta{
    font-size: 13px;
    color: #969696;
}
.user .meta i{
    font-size: 13px;
    margin: 0;
    margin-right: 5px;
}
.user .meta a{
    margin-right: 20px;
}
.user .meta a:hover{
    color: black !important;
}
.caozuo{
    float: right;
    font-size: 13px;
    color: #969696;
}
.caozuo i{
    cursor: pointer;
}
.kuai ul{
    position: absolute;
    top: 30px;
    right: 10px;
    background-color: #fff;
    z-index: 1000;
    border: 1px solid #eaeaea;
    box-shadow: 0 2px 8px rgba(0,0,0,.1);
}
.kuai ul li{
    padding: 5px 20px;
    font-size: 15;
    cursor: pointer;
}
.kuai ul li i{
    margin-right: 5px;
}
.kuai ul li:hover{
    background-color: #eaeaea;
}


.two{
    widows: 100%;
}
.two .chat-top{
    position: relative;
    border-bottom: 1px solid #eaeaea;
    padding: 10px 0;
    /* position: fixed; */
    width: 100%;
    z-index: 1;
    min-height: 35px;
    margin-bottom: 20px;
    padding-bottom: 10px;
    text-align: center;
    background-color: #fff;
    border-bottom: 1px solid #f0f0f0;
}
.two .chat-top .back-to-list{
    position: absolute;
    top: 10px;
    left: 0;
    font-size: 14px;
    color: #969696 !important;
}
.two .chat-top b{
    display: inline-block;
    padding: 0 140px 0 200px;
    font-size: 14px;
}
.two .chat-top div{
    float:right;
}
.two .chat-top div ul{
    position: absolute;
    top: 30px;
    right: 0px;
    background-color: #fff;
    z-index: 1000;
    border: 1px solid #eaeaea;
    box-shadow: 0 2px 8px rgba(0,0,0,.1);
}
.two .chat-top div ul li{
    padding: 5px 20px;
    font-size: 15;
    cursor: pointer;
}
.two .chat-top div ul li i{
    margin-right: 5px;
}
.two .chat-top div ul li:hover{
    background-color: #eaeaea;
}
.two .message-show{
    width: 100%;
    padding-top: 55px;
    margin-bottom: 50px;
    overflow: hidden;
}
.message-show li {
    margin-bottom: 15px;
    overflow:hidden;
}
.two .message-show .message-list .avatar{
    width:40px;
    height:40px;
    border-radius: 50%;
}
.two .message-show .message-list .message-l .avatar{
    float: left;
}
.two .message-show .message-list .message-r .avatar{
    float: right;
}
.two .message-show .message-list .avatar img{
    width: 100%;
    height: 100%;
    
}
.message-show li div {
    position: relative;
    display: block;
    margin: 4px 56px 0;
    min-height: 39px;
}
.message-show li div .content {
    position: relative;
    padding: 8px 12px;
    font-size: 14px;
    border: 1px solid;
    word-break: break-word!important;
    word-break: break-all;
    line-height: 1.5;
    display: table-cell;
    background-color: #e7f1fc;
    border-color: #bad0e9;
}
.message-show .message-list .message-l div {
    position: relative;
    display: block;
    margin: 4px 56px 0;
    min-height: 39px;
    border-radius: 0 4px 4px 4px;
}
.message-show .message-r div .content {
    float: right;
    min-height: 39px;
    background-color: #eee;
    border-color: #d9d9d9;
    border-radius: 4px 0 4px 4px;
}
.message-show .time {
    margin-top: 2px;
    font-size: 12px;
    color: #d9d9d9;
}
.message-show .message-l .time {
    margin-left: 56px;
}
.message-show .message-r .time {
    float: right;
    margin-right: 56px;
}
.main .message-show li div:after,.main .message-show li div:before {
    position: absolute;
    top: 0;
    content: "";
    display: inline-block
}

.main .message-show li div:after {
    top: 1px
}
.main .message-show .message-r div:after,.main .message-show .message-r div:before {
    right: -9px;
    border-right: 9px solid transparent;
    border-top: 16px solid #d9d9d9
}

.main .message-show .message-r div:after {
    right: -7px;
    border-top: 16px solid #eee
}
.main .message-show .message-l div:after,.main .message-show .message-l div:before {
    left: -9px;
    border-left: 9px solid transparent;
    border-top: 16px solid #bad0e9
}

.main .message-show .message-l div:after {
    left: -7px;
    border-top: 16px solid #e7f1fc
}



.con .two .write-message{
    /* position: fixed; */
    width: 100%;
    bottom: 0;
    margin-top: 15px;
    background-color: #fff;
}
.two .write-message .btn-send {
    float: right;
    width: 78px;
    margin: 10px 0;
    padding: 8px 18px;
    font-size: 16px;
    border: none;
    border-radius: 20px;
    color: #fff;
    background-color: #42c02e;
    cursor: pointer;
    outline: none;
    display: block;
}
.two .write-message .hint {
    padding-top: 3px;
    font-size: 13px;
    color: #969696;
    margin-top: 15px;
}
</style>