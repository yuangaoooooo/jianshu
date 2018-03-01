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
                                <span slot="label"><i class="fa fa-file-text "></i>文章</span>
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
                                <div class="content">
                                    <div class="author">
                                        <nuxt-link class="avatar" to="/u/123">
                                            <img src="../assets/img/default-avatar.jpg" alt="">                                          
                                        </nuxt-link>
                                        <div class="info">
                                            <nuxt-link to="/u/123" class="nickname">
                                                grooooooter
                                            </nuxt-link>
                                            <span class="time">
                                                02.09 20：00
                                            </span>
                                        </div>
                                    </div>
                                    <nuxt-link class="title" to="/p/123">
                                        2018-02-02
                                    </nuxt-link>
                                    <p class="abstract">
                                        过年好啊
                                    </p>
                                    <div class="meta">
                                        <nuxt-link to="/p/123">
                                            <i class="fa fa-eye"></i>
                                            0
                                        </nuxt-link>
                                        <nuxt-link to="/p/123">
                                            <i class="fa fa-comment"></i>
                                            0
                                        </nuxt-link>
                                        <span>
                                            <i class="fa fa-heart"></i>
                                            0
                                        </span>
                                    </div>
                                </div>
                            </el-tab-pane>
                            <el-tab-pane name="second">
                                <span slot="label"><i class="fa fa-bell "></i>动态</span>
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
                                <div class="content">
                                    <div class="author">
                                        <nuxt-link class="avatar" to="/u/123">
                                            <img src="../assets/img/default-avatar.jpg" alt="">                                          
                                        </nuxt-link>
                                        <div class="info">
                                            <nuxt-link to="/u/123" class="nickname">
                                                grooooooter
                                            </nuxt-link>
                                            <span class="time">
                                              发表了文章 02.09 20：00
                                            </span>
                                        </div>
                                    </div>
                                    <nuxt-link class="title" to="/p/123">
                                        2018-02-02
                                    </nuxt-link>
                                    <p class="abstract">
                                        过年好啊
                                    </p>
                                    <div class="meta">
                                        <nuxt-link to="/p/123">
                                            <i class="fa fa-eye"></i>
                                            0
                                        </nuxt-link>
                                        <nuxt-link to="/p/123">
                                            <i class="fa fa-comment"></i>
                                            0
                                        </nuxt-link>
                                        <span>
                                            <i class="fa fa-heart"></i>
                                            0
                                        </span>
                                    </div>
                                </div>
                            </el-tab-pane>
                            <el-tab-pane name="third">
                                <span slot="label"><i class="fa fa-comments"></i>最新评论</span>
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
                                <div class="content">
                                    <div class="author">
                                        <nuxt-link class="avatar" to="/u/123">
                                            <img src="../assets/img/default-avatar.jpg" alt="">                                          
                                        </nuxt-link>
                                        <div class="info">
                                            <nuxt-link to="/u/123" class="nickname">
                                                grooooooter
                                            </nuxt-link>
                                            <span class="time">
                                                02.09 20：00
                                            </span>
                                        </div>
                                    </div>
                                    <nuxt-link class="title" to="/p/123">
                                        2018-02-02
                                    </nuxt-link>
                                    <p class="abstract">
                                        过年好啊
                                    </p>
                                    <div class="meta">
                                        <nuxt-link to="/p/123">
                                            <i class="fa fa-eye"></i>
                                            0
                                        </nuxt-link>
                                        <nuxt-link to="/p/123">
                                            <i class="fa fa-comment"></i>
                                            0
                                        </nuxt-link>
                                        <span>
                                            <i class="fa fa-heart"></i>
                                            0
                                        </span>
                                    </div>
                                </div>
                            </el-tab-pane>
                            <el-tab-pane name="fourth">
                                <span slot="label"><i class="fa fa-trophy"></i>热门</span>
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
                                <div class="content">
                                   
                                    <div class="author">
                                        <nuxt-link class="avatar" to="/u/123">
                                            <img src="../assets/img/default-avatar.jpg" alt="">                                          
                                        </nuxt-link>
                                        <div class="info">
                                            <nuxt-link to="/u/123" class="nickname">
                                                grooooooter
                                            </nuxt-link>
                                            <span class="time">
                                                02.09 20：00
                                            </span>
                                        </div>
                                    </div>
                                    <nuxt-link class="title" to="/p/123">
                                        2018-02-02
                                    </nuxt-link>
                                    <p class="abstract">
                                        过年好啊
                                    </p>
                                    <div class="meta">
                                        <nuxt-link to="/p/123">
                                            <i class="fa fa-eye"></i>
                                            0
                                        </nuxt-link>
                                        <nuxt-link to="/p/123">
                                            <i class="fa fa-comment"></i>
                                            0
                                        </nuxt-link>
                                        <span>
                                            <i class="fa fa-heart"></i>
                                            0
                                        </span>
                                    </div>
                                </div>
                            </el-tab-pane>
                        </el-tabs>
                    </div>
                </div>
                <div class="col-4 me-aside">
                    <span class="title">个人介绍</span>
                    <a class="bianji" href="javacsript:void(0)"  @click="showedit=true">
                        <span class="fa fa-pencil"></span>编辑
                    </a>
                    <form action=""  v-if="showedit">
                        <textarea></textarea>
                        <input type="button" value="保存" class="btn btn-hollow" @click="showedit=false">
                        <a href="javacsript:void(0)" @click="showedit=false">取消</a>
                    </form>
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
                    <nuxt-link to="/">
                        <span class="fa fa-plus"></span>创建一个新专题
                    </nuxt-link>
                  </p>
                  <hr>
                  <p class="zuanti">
                      我的文集
                  </p>
                  <p class="book">
                        <nuxt-link to="/">
                            <span class="fa fa-book"></span>日记本
                        </nuxt-link>
                  </p>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
    import myHeader from '../components/myHeader.vue'
export default {
    name:'me',
    components:{
        myHeader
    },
    data () {
        return {
            activeName: 'first',
            showedit:false,
        }
    },
    methods: {
        
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
.index .me-aside form{
    margin-bottom: 20px;
    margin-top: 10px;
}
.index .me-aside  form textarea{
    width:100%;
    height:125px;
    font-size: 14px;
    margin-bottom: 5px;
    padding:5px 10px;
    border:1px solid #ccc;
    border-radius: 4px;
    display:inline-block;
    vertical-align: top;
    outline-style: none;
    resize: none;
    font-size:13px;
}
.index .me-aside form input{
    padding:5px 20px;
    font-size: 14px;
    border: 1px solid #42c02e;
    background-color: #fff;
    color: #42c02e !important;
    border-radius: 20px;
}
.index .me-aside form a{
    margin-left: 10px;
    font-size: 14px;
    color:#969696;
    vertical-align: middle;
    line-height: 34px;
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