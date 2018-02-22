<template>
    <div @click.stop="isshow=false">
        <my-header></my-header>
        <div class="main">
            <el-tabs tab-position="left" style="height: 200px;">
                <el-tab-pane>
                    <span slot="label"><i class="fa fa-comment-o"></i>评论</span>
                    <div class="con">
                        <div class="top">
                            收到的评论
                        </div>
                        <div class="user">
                            <nuxt-link to="/m/123" class="avatar">
                                <img src="../../assets/img/default-avatar.jpg" alt="">
                            </nuxt-link>
                            <div class="in">
                                <div class="who">a23546wd 评论了你的文章<span>《2018-02-09》</span></div>
                                <div class="time">2018.02.10 08:26</div>
                            </div>
                            <div class="neiron">
                                guonianhao
                            </div>
                            <div class="meta">
                                <i class="fa fa-comment-o"></i>
                                <a href="javascript:;">回复</a>
                                <i class="fa fa-share"></i>
                                <a href="javascript:;">查看对话</a>
                            </div>
                        </div>
                    </div>
                </el-tab-pane>
                <el-tab-pane>
                    <span slot="label"><i class="fa fa-envelope-open-o"></i>简信</span>
                    <div class="con">
                        <div class="top">
                            全部简信
                        </div>
                        <div class="user">
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
                </el-tab-pane>
                <el-tab-pane>
                    <span slot="label"><i class="fa fa-hand-o-up"></i>投稿请求</span>
                    <div class="con">
                        <div class="top">全部投稿请求</div>
                    </div>
                </el-tab-pane>
                <el-tab-pane>
                    <span slot="label"><i class="fa fa-heart-o"></i>喜欢和赞</span>
                    <div class="con">
                        <div class="top">收到的喜欢和赞</div>
                    </div>
                </el-tab-pane>
                <el-tab-pane>
                    <span slot="label"><i class="fa fa-user-o "></i>关注</span>
                    <div class="con">
                        <div class="top">全部关注</div>
                        <div class="content-placeholder-guanzhu">
                                <div class="avatar"></div>
                                <div class="title">
                                    <div class="name"></div>
                                    <div class="jianjie"></div>
                                </div>
                                <div class="anniu"></div>
                            </div>
                            <div class="content-guanzhu">
                                <div class="info">
                                    <nuxt-link class="avatar" to="/u/123">
                                        <img src="../../assets/img/default-avatar.jpg" alt="">
                                    </nuxt-link>
                                    <a class="btn btn-success" href="javascript:void(0)":class="followObj"
                                    @click="isFollow" @mouseover="noFollow" @mouseleave="beFollow">
                                        <i class="fa" :class="iconObj" ref="icon"></i>
                                        <span ref="followWord" >关注</span>
                                    </a>
                                    <nuxt-link class="title" to="/u/123">
                                        as51325asd 关注了你
                                    </nuxt-link>
                                    <p>
                                        2017.02.09 09.36
                                    </p>
                                </div>
                            </div>
                    </div>
                   
                </el-tab-pane>
            </el-tabs>
        </div>
    </div>
</template>
<script>
    import myHeader from '../../components/myHeader.vue'
    export default {
        name:'pinlun',
        components:{
            myHeader
        },
        data () {
            return {
                isshow:false,
                followObj:{
                    'follow':true,
                    'following':false
                },
                iconObj:{
                    'fa-plus-square-o':true,
                    'fa-check':false
                },
            }
        },
        methods: {
            isFollow:function(){
                let word = this.$refs.followWord.innerHTML;
                // 这里预留关注的ajax操作
                this.followObj.follow = !this.followObj.follow;
                this.followObj.following = !this.followObj.following;
                this.iconObj['fa-plus-square-o'] = !this.iconObj['fa-plus-square-o'];
                this.iconObj['fa-check'] = !this.iconObj['fa-check'];
                
                this.$refs.followWord.innerHTML = word == '关注' ? '已关注' : '关注';
            
            },
            noFollow:function(){
                let word = this.$refs.followWord.innerHTML;
                if(word == '已关注'){
                    this.$refs.followWord.innerHTML = '取消关注';
                    this.$refs.icon.className = 'fa fa-close';
                }
            },
            beFollow:function(){
                let word = this.$refs.followWord.innerHTML;
                if(word == '取消关注'){
                    this.$refs.followWord.innerHTML = '已关注';
                    this.$refs.icon.className = 'fa fa-check';
                }
            },
        },

    }
</script>
<style scoped>
@media (min-width:992px){
    .main {
        width: 960px;
}
}
@media (max-width:1080px){
    .main {
        width: 750px;
    }
    .in{
        width: 360px;
    }
}
.main{
    margin: 0 auto;
    padding-top: 30px;
}
.el-tabs{
    height: 100% !important;
}
.el-tabs .el-tabs__nav-scroll span{
    font-size: 16px;
}
.el-tabs i{
    font-size: 20px;
    margin-right: 10px;
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
.user{
    padding: 20px 0 20px 20px;
    border-bottom: 1px solid #eaeaea;
    position: relative;
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
.kuai{
    position: absolute;
    top: 95px;
    right: 180px;
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
.kuai ul li:hover{
    background-color: #eaeaea;
}



.content-placeholder-guanzhu .avatar{
    width: 48px;
    height: 48px;
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
.content-placeholder-guanzhu .anniu{
    float: right;
    width: 100px;
    height: 40px;
    padding: 8px 0;
    background-color: #eaeaea;
    border-radius: 20px;
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

.content-guanzhu{
    border-bottom: 1px solid #ccc;
    margin-top: 20px;
}
.content-guanzhu .follow{
    color: #ffffff !important;
    font-size: 12px;
    border-radius: 20px;
    background: #42c02e !important;
    padding: 1px 10px 1px 7px;
}
.content-guanzhu .following{
    background:#fff;
    color:#969696;
    border:1px solid #ccc;
    font-size:12px;
    border-radius: 20px;
    padding:1px 8px 1px 6px;
}
.content-guanzhu .btn{
    float: right;
    box-shadow: none;
    width: 100px;
    padding: 8px 0;
    font-size: 16px;
}
.content-guanzhu .following{
    background: none;
}

.content-guanzhu .avatar {
    width: 48px;
    height: 48px;
    margin-right: 10px;
    float: left;
    border-radius: 50%;
}
 .content-guanzhu .title{
    font-size: 15px;
    line-height: 1.8;
    font-weight: 700;
    color: #969696 !important;
    margin-right: 5px;
}
.content-guanzhu .info{
    margin-bottom: 20px;
}
 .content-guanzhu .info img{
    
}
 .content-guanzhu .info>i{
    color: #3194d0;
    font-size: 15px;
}
 .content-guanzhu .info p{
    color: #969696;
    margin-bottom: 0;
    font-size: 12px;
}
</style>