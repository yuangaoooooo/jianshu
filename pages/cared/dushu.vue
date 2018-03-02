<template>
    <div>
        <div class="con">
            <div class="placeholder">
                <div class="title-placeholder">
                    <div class="head">
                        <div class="avatar"></div>
                        <div class="info">
                            <div class="title"></div>
                            <div class="jianjie"></div>
                        </div>
                        <div class="zuanti"></div>
                        <div class="tougao"></div>
                    </div>
                </div>
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
            </div>
            <div class="main-top">
                <div class="head">
                    <nuxt-link to="/" class="avatar">
                        <img src="../../assets/img/default-avatar.jpg" alt="">
                    </nuxt-link>
                    <div class="info">
                        <nuxt-link to="/" class="title">散文随笔</nuxt-link>
                        <div class="jianjie">收录了186930篇文章</div>
                    </div>
                    <nuxt-link to="/" class="zuanti anniu">专题主页</nuxt-link>
                    <nuxt-link to="/" class="tougao anniu">投稿</nuxt-link>
                </div>
            </div>
            <ul class="trigger-menu">
                <li :class="{active:currentTab == 'MyArticle'}">
                    <a href="javascript:void(0)" @click="toggleTab('MyArticle')">
                        <i class="fa fa-file-text"></i>
                        文章
                    </a>
                </li>
                <li :class="{active:currentTab == 'MyNew'}">
                    <a href="javascript:void(0)" @click="toggleTab('MyNew')">
                        <i class="fa fa-bell"></i>
                        动态
                    </a>
                </li>
                <li :class="{active:currentTab == 'MyComment'}">
                    <a href="javascript:void(0)" @click="toggleTab('MyComment')">
                        <i class="fa fa-comments"></i>
                        最新评论
                    </a>
                </li>
                <li :class="{active:currentTab == 'MyHot'}">
                    <a href="javascript:void(0)" @click="toggleTab('MyHot')">
                        <i class="fa fa-fire"></i>
                        热门
                    </a>
                </li>
            </ul>
            <div id="list-container">
                <!--动态组件-->
                <component :is="currentTab" keep-alive></component>
            </div>
            <a href="javascript:;" class="read-more">
                阅读更多
            </a>
        </div>
    </div>
</template>
<script>
    import MyArticle from '@/components/user/MyArticle'
    import MyNew from '@/components/user/MyNew'
    import MyComment from '@/components/user/MyComment'
    import MyHot from '@/components/user/MyHot'
    export default {
        name:'dushu',
        components:{
            MyArticle,
            MyNew,
            MyHot,
            MyComment
        },
        data () {
            return {
                currentTab:'MyArticle',
            }
        },
        methods: {
            toggleTab:function(tab){
                this.currentTab = tab;
            },
        }

    }
</script>
<style scoped>
@media (min-width:992px){
    .con{
        margin-left: 260px;
    }
    
}

@media (max-width:1080px){
    .con{
        margin-left: 200px;
    }
}  
.con{
    padding-left: 20px;
}
.title-placeholder{
    padding-bottom: 20px;
    border-bottom: 1px solid #eaeaea;
}
.title-placeholder .head .avatar{
    width: 80px;
    height: 80px;
    border-radius: 5px;
    background-color: #ebebeb;
    display: inline-block;
    vertical-align: middle;
    margin-right: 10px;
}
.title-placeholder .head .info{
    display: inline-block;
    vertical-align: middle;
}
.title-placeholder .head .info .title{
    background-color: #ebebeb;
    width: 83px;
    height: 23px;
}
.title-placeholder .head .info .jianjie{
    width: 150px;
    height: 16px;
    background-color: #ebebeb;
    margin-top: 10px;    
}
.title-placeholder .head .tougao{
    background-color: #ebebeb;
    vertical-align: middle;
    display: inline-block;
    width: 62px;
    height: 37px;
    border-radius: 20px;
    float: right;
    margin-right: 30px;
    margin-top: 20px;
}
.title-placeholder .head .zuanti{
    background-color: #ebebeb;
    width: 100px;
    height: 37px;
    border-radius: 20px;
    float: right;
    margin-top: 20px;
}
.content-placeholder{
    padding-top: 20px;
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

.main-top{
    margin-bottom: 20px;
}
.main-top .head .avatar{
    width: 80px;
    height: 80px;
    border-radius: 5px;
    display: inline-block;
    vertical-align: middle;
    margin-right: 10px;
}
.main-top .head .avatar img{
    border-radius: 5px;
}
.main-top .head .info{
    display: inline-block;
    vertical-align: middle;
}
.main-top .head .info .title{
    font-size: 21px;
    font-weight: 700;
}
.main-top .head .info .jianjie{
    font-size: 14px;
    color: #969696;
    margin-top: 10px;    
}
.main-top .head .tougao{
    vertical-align: middle;
    display: inline-block;
    width: 62px;
    height: 37px;
    border-radius: 20px;
    float: right;
    margin-right: 30px;
    margin-top: 20px;
    border: 1px solid rgba(59,194,29,.7);
    color: #42c02e!important;
    text-align: center;
    line-height: 37px;
}
.main-top .head .zuanti{
    width: 100px;
    height: 37px;
    border-radius: 20px;
    float: right;
    margin-top: 20px;
    border: 1px solid rgba(59,194,29,.7);
    color: #42c02e!important;
    text-align: center;
    line-height: 37px;
}
.main-top .head .anniu:hover{
    background-color: #f5fcf3;
}

.el-tabs .el-tabs__nav-scroll span{
    /* color:#969696; */
    font-size: 16px;
}
.el-tabs i{
    margin-right: 10px;
}
.content{
    margin-top: 10px;
    border-bottom: 1px solid #ebebeb;
}
 .content .author .avatar{
    display: inline-block;
    vertical-align: middle;
    margin-right: 10px;
    
}
 .content .author .info{
    display: inline-block;
    vertical-align: middle;
}
 .content .author .info .nickname{
    color: #333;
    font-size: 13px;
}
 .content .author .info .time{
    font-size: 13px;
    color: #969696;
}
 .content .title{
    font-size: 18px;
    font-weight: 700;
    color: #969696 !important;
    line-height: 1.5;
    margin-top: 10px;
} 
 .content .abstract{
    font-size: 13px;
    margin-top: 10px;
}
 .content .meta{
    font-size: 12px;
    font-weight: 400;
    color: #969696;
    margin-bottom: 20px;
}

 .content .meta i:hover{
    color: #787878;
}
 .content .meta a{
    margin-right: 10px;
}
.read-more{
    width: 100%;
    height: 40px;
    margin: 30px auto 60px;
    padding: 10px 15px;
    text-align: center;
    font-size: 15px;
    border-radius: 20px;
    color: #fff;
    background-color: #a5a5a5;
    display: block;
}
</style>