<template>
    <div>
        <my-header></my-header>
        <div class="index my-container">
            <div class="row">
                <div class="col-8 me-main">
                    <div class="main-top">
                        <nuxt-link class="avatar" to="/u/me">
                            <img src="../assets/img/default-avatar.jpg" alt="">
                        </nuxt-link>
                        <div class="xinxi">
                            <div class="title">
                                <nuxt-link class="name" to="/u/me">grooooooter</nuxt-link>
                            </div>
                            <div class="info">
                                <ul>
                                    <li>
                                        <div class="meta-block">
                                            <nuxt-link to="/u/me">
                                                <p>11</p>
                                                <span>
                                                    关注<span class="fa fa-angle-right"></span>
                                                </span>
                                            </nuxt-link>
                                        </div>     
                                    </li>
                                    <li>
                                        <div class="meta-block">
                                            <nuxt-link to="/u/me">
                                                <p>0</p>
                                                <span>
                                                    粉丝<span class="fa fa-angle-right"></span>
                                                </span>
                                            </nuxt-link>
                                        </div>     
                                    </li>
                                    <li>
                                        <div class="meta-block">
                                            <nuxt-link to="/u/me">
                                                <p>1</p>
                                                <span>
                                                    文章<span class="fa fa-angle-right"></span>
                                                </span>
                                            </nuxt-link>
                                        </div>     
                                    </li>
                                    <li>
                                        <div class="meta-block"> 
                                            <p>4</p>
                                            <span>
                                                字数
                                            </span>
                                        </div>     
                                    </li>
                                    <li>
                                        <div class="meta-block"> 
                                            <p>0</p>
                                            <span>
                                                收获和喜欢
                                            </span>
                                        </div>     
                                    </li>
                                </ul>
                            </div>
                        </div>
                    </div>
                    <div class="trigger-menu">
                        <el-tabs v-model="activeName">
                            <el-tab-pane name="first">
                                <span slot="label">关注的专题/文章/连载 31</span>
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
                                            <img src="../assets/img/default-avatar.jpg" alt="">
                                        </nuxt-link>
                                        <a class="btn btn-success" href="javascript:void(0)":class="followObj"
                                        @click="isFollow" @mouseover="noFollow" @mouseleave="beFollow">
                                            <i class="fa" :class="iconObj" ref="icon"></i>
                                            <span ref="followWord" >关注</span>
                                        </a>
                                        <nuxt-link class="title" to="/u/123">
                                            武侠江湖
                                        </nuxt-link>
                                        <p>
                                            <span class="lan">简书</span>
                                            收录了265305篇文章，198520人关注
                                        </p>
                                    </div>
                                </div>
                                
                            </el-tab-pane>
                            <el-tab-pane name="second">
                                <span slot="label">喜欢的文章 3</span>
                                <div class="content-placeholder">
                                    <div class="author">
                                        <div class="avatar"></div>                                         
                                        <div class="info"></div>
                                    </div>
                                    <div class="title"></div>
                                    <div class="abstract ab1"></div>
                                    <div class="abstract ab2"></div>
                                    <div class="abstract ab3"></div>
                                    <div class="img"></div>
                                    <div class="meta">
                                        <i class="fa fa-eye"></i>
                                        <span></span>
                                        <i class="fa fa-comment"></i>
                                        <span></span>
                                        <i class="fa fa-heart"></i>
                                        <span></span>
                                    </div>
                                </div>
                                <div class="content" @mouseover="islike=true" @mouseleave="islike=false">
                                    <div class="author">
                                        <nuxt-link class="avatar" to="/u/123">
                                            <img src="../assets/img/default-avatar.jpg" alt="">                                          
                                        </nuxt-link>
                                        <div class="info">
                                            <nuxt-link to="/u/123" class="nickname">
                                                用户
                                            </nuxt-link>
                                            <span class="time">
                                                20：00
                                            </span>
                                        </div>
                                    </div>
                                    <nuxt-link class="title" to="/p/123">
                                        如何把书中的知识转化成能力？这是我见过的最好回答
                                    </nuxt-link>
                                    <p class="abstract">
                                        随着知识经济的兴起，读书的重要性得到了大家的普遍认同，于是市场上出现很多读书方法，比如速度、多读、慢读、列读......不管你采用哪一种读书方法，最终都要回归到“行动”二字上，正如陆...
                                    </p>
                                    <div class="meta">
                                        <nuxt-link to="/p/123">
                                            <i class="fa fa-eye"></i>
                                            2590
                                        </nuxt-link>
                                        <nuxt-link to="/p/123">
                                            <i class="fa fa-comment"></i>
                                            500
                                        </nuxt-link>
                                        <span>
                                            <i class="fa fa-heart"></i>
                                            539
                                        </span>
                                        <a href="javascript:;" class="quxiao" v-if="islike">取消喜欢</a>
                                    </div>
                                </div>
                            </el-tab-pane> 
                        </el-tabs>
                    </div>
                </div>
                <div class="col-4 me-aside">
                  <span class="title">个人介绍</span>
                  <nuxt-link class="bianji" to="/u/me">
                        <span class="fa fa-pencil"></span>编辑
                  </nuxt-link>
                  <hr>
                  <p class="gzxh">
                    <nuxt-link to="/u/me">
                        <span class="fa fa-th-large"></span>
                        我关注的专题/文集/连载
                    </nuxt-link>
                  </p>
                  <p class="gzxh">
                    <nuxt-link to="/u/me">
                        <span class="fa fa-heart-o"></span>
                        我喜欢的文章
                    </nuxt-link>
                  </p>
                  <hr>
                  <p class="zuanti">
                    我创建的专题
                  </p>
                  <p class="zuanti lu">
                    <span class="fa fa-plus"></span>创建一个新专题
                  </p>
                  <hr>
                  <p class="zuanti">
                      我的文集
                  </p>
                  <p class="book">
                        <span class="fa fa-book"></span>日记本
                  </p>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
    import myHeader from '../components/myHeader.vue'
export default {
    name:'like',
    components:{
        myHeader
    },
    data () {
        return {
            activeName: 'first',
            islike:false,
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
.index .me-main .main-top{
    margin-bottom:20px; 
    height: 82px;
}
.index .me-main .main-top .avatar{
    width: 80px;
    height: 80px;
    float: left;
    
}
.index .me-main .main-top .avatar img{
    width: 100%;
    height: 100%;
    border-radius: 50%;
    vertical-align: bottom;
}
.index .me-main .main-top .xinxi{
    float: left;
}
.index .me-main .main-top .title{
    padding: 0 0 0 30px;
}
.index .me-main .main-top .title .name{
    display: inline;
    font-size: 21px;
    font-weight: 700; 
    vertical-align: middle;
}

.index .me-main .main-top .info{
    padding: 5px 0 0 30px;
    vertical-align: middle;
}
.index .me-main .main-top .info ul li{
    display: inline-block;
    line-height: 20px;
}
.index .me-main .main-top .info ul li .meta-block{
    font-size: 12px;
    margin: 0 7px 6px 0;
    padding: 0 7px 0 0;
    border-right: 1px solid #f0f0f0;
}
.index .me-main .main-top .info ul li:last-child .meta-block{
    border: none;
}
.index .me-main .main-top .info ul li .meta-block p{
    margin: 0;
    font-size: 15px;
    color:#333;
}
.index .me-main .main-top .info ul li .meta-block span {
    color: #969696;
}
.index .me-main .main-top .info ul li .meta-block span span{
    margin-left: 5px; 
}
.el-tabs .el-tabs__nav-scroll span{
    /* color:#969696; */
    font-size: 16px;
}
.el-tabs i{
    margin-right: 10px;
}

.content-placeholder-guanzhu .avatar{
    width: 48px;
    height: 48px;
    margin-right: 10px;
    display: inline-block;
    vertical-align: middle;
    background-color: #eaeaea;
    border-radius: 5px;
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

.trigger-menu .content-guanzhu{
    border-bottom: 1px solid #ccc;
    margin-top: 20px;
}
.trigger-menu .content-guanzhu .follow{
    color: #ffffff !important;
    font-size: 12px;
    border-radius: 20px;
    background: #42c02e !important;
    padding: 1px 10px 1px 7px;
}
.trigger-menu .content-guanzhu .following{
    background:#fff;
    color:#969696;
    border:1px solid #ccc;
    font-size:12px;
    border-radius: 20px;
    padding:1px 8px 1px 6px;
}
.trigger-menu .content-guanzhu .btn{
    float: right;
    box-shadow: none;
    width: 100px;
    padding: 8px 0;
    font-size: 16px;
}
.trigger-menu .content-guanzhu .following{
    background: none;
}

.trigger-menu .content-guanzhu .avatar {
    width: 48px;
    height: 48px;
    margin-right: 10px;
    float: left;
}
.trigger-menu .content-guanzhu .title{
    font-size: 15px;
    line-height: 1.8;
    font-weight: 700;
    color: #333;
    margin-right: 5px;
}
.trigger-menu .content-guanzhu .info{
    margin-bottom: 20px;
}
.trigger-menu .content-guanzhu .info img{
    border-radius: 5px;
}
.trigger-menu .content-guanzhu .info>i{
    color: #3194d0;
    font-size: 15px;
}
.trigger-menu .content-guanzhu .info p{
    color: #969696;
    margin-bottom: 0;
    font-size: 12px;
}
.lan{
    color: #3194d0;
}




.content-placeholder{
    position: relative;
}
.content-placeholder .author .avatar{
    width: 32px;
    height: 32px;
    background-color: #ebebeb;
    border-radius: 50%;
    display: inline-block;
    vertical-align: middle;
    margin-right: 5px;
}
.content-placeholder .author .info{
    width: 80px;
    height: 16px;
    display: inline-block;
    background-color: #ebebeb;
    vertical-align: middle;
}
.content-placeholder .title{
    width: 180px;
    height: 19px;
    background-color: #ebebeb;
    margin-top: 10px;
}
.content-placeholder .abstract{
    width: 70%;
    height: 16px;
    background-color: #ebebeb;
    margin-top: 10px;
}
.content-placeholder .ab1{
    animation: loading 1s ease-in-out infinite;
}
.content-placeholder .ab2{
    animation: loading 1s ease-in-out -.5s infinite;
}
.content-placeholder .ab3{
    width: 35%;
    animation: loading2 1s ease-in-out -.5s infinite;
}
.content-placeholder .img{
    position: absolute;
    top:50px;
    right: 10px;
    width: 120px;
    height: 100px;
    background-color: #ebebeb;
    border-radius: 5px;
}
.content-placeholder .meta{
    margin-top: 10px;
}
.content-placeholder .meta i{
    color: #ebebeb;
    font-size: 12px;
    margin: 3px;
}
.content-placeholder .meta span{
    display: inline-block;
    width: 40px;
    height: 16px;
    background-color: #ebebeb;
    vertical-align: middle;
}
@keyframes loading{
    0%{
        width: 35%;
    }
    25%{
        width: 70%;
    }
    50%{
        width: 70%;
    }
    100%{
        width: 35%;
    }
}
@keyframes loading2{
    0%{
        width: 10%;
    }
    25%{
        width: 35%;
    }
    50%{
        width: 35%;
    }
    100%{
        width: 10%;
    }
}
.el-tabs .content{
    margin-top: 20px;
    border-bottom: 1px solid #ebebeb;
}
.el-tabs .content .author .avatar{
    display: inline-block;
    vertical-align: middle;
    margin-right: 10px;
    
}
.el-tabs .content .author .info{
    display: inline-block;
    vertical-align: middle;
}
.el-tabs .content .author .info .nickname{
    color: #333;
    font-size: 13px;
}
.el-tabs .content .author .info .time{
    font-size: 13px;
    color: #969696;
}
.el-tabs .content .title{
    font-size: 18px;
    font-weight: 700;
    color: #969696 !important;
    line-height: 1.5;
    margin-top: 10px;
} 
.el-tabs .content .abstract{
    font-size: 13px;
    margin-top: 10px;
}
.el-tabs .content .meta{
    font-size: 12px;
    font-weight: 400;
    color: #969696;
    margin-bottom: 20px;
}
.el-tabs .content .meta i{
    margin: 0;
}
.el-tabs .content .meta i:hover{
    color: #787878;
}
.el-tabs .content .meta a{
    margin-right: 10px;
}
.el-tabs .content .meta .quxiao{
    margin-left: 10px;
}

/*  */
.index .me-aside .title{
    font-size: 14px;
    color: #969696;
}
.index .me-aside .bianji{
    font-size: 14px;
    color: #969696 !important;
    float: right;
}
.index .me-aside .bianji span{
    margin-right: 5px;
}
.index .me-aside .gzxh a{
    font-size: 14px;
}
.index .me-aside .gzxh span{
    font-size: 21px;
    vertical-align: middle;
    margin-right: 10px;
}
.index .me-aside .zuanti{
    font-size: 14px;
    color: #969696;
}
.index .me-aside .zuanti span{
    margin-right: 5px;
}
.index .me-aside .lu{
    color: green;
}
.index .me-aside .book{
    font-size: 14px;
}
.index .me-aside .book span{
    color: #969696;
    margin-right: 10px;
}
</style>