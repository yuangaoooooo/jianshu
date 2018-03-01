<template>
        <div>
            <my-header></my-header>
            <div class="person my-container">
                <div class="row">
                    <div class="col-8 main">
                        <div class="main-top">
                            <nuxt-link class="avatar" to="/u/123">
                                <img src="~assets/img/default-avatar.jpg">
                            </nuxt-link>
                            <a href="javascript:void(0)" class="btn btn-success off user-follow-button"
                            :class="followObj"
                            @click="isFollow" @mouseover="noFollow" @mouseleave="beFollow"
                            >
                                <i class="fa" :class="iconObj" ref="icon"></i>
                                <span ref="followWord" >关注</span>
                            </a>
                            <a class="btn btn-hollow" href="/notifications">
                                发简信
                            </a>
                            <div class="title">
                                <nuxt-link class="name" to="/u/123">
                                    grooooooter
                                </nuxt-link>
                                <i class="fa fa-mars"></i>
                            </div>
                            <div class="info">
                                <ul>
                                    <li>
                                        <div class="meta-block">
                                            <nuxt-link to="/users/123/following">
                                                <p>88</p>
                                                关注
                                                <i class="fa fa-angle-right"></i>
                                            </nuxt-link>
                                        </div>
                                    </li>
                                    <li>
                                        <div class="meta-block">
                                            <nuxt-link to="/users/123/followers">
                                                <p>16</p>
                                                粉丝
                                                <i class="fa fa-angle-right"></i>
                                            </nuxt-link>
                                        </div>
                                    </li>
                                    <li>
                                        <div class="meta-block">
                                            <nuxt-link to="/u/123">
                                                <p>32</p>
                                                文章
                                                <i class="fa fa-angle-right"></i>
                                            </nuxt-link>
                                        </div>
                                    </li>
                                    <li>
                                        <div class="meta-block">
                                            <p>5000</p>
                                            字数
                                        </div>
                                    </li>
                                    <li>
                                        <div class="meta-block">
                                            <p>100</p>
                                            收获喜欢
                                        </div>
                                    </li>
                                </ul>
                            </div>
                        </div>
                        <ul class="trigger-menu">
                            <li :class="{active:currentTab == 'FollowUser'}">
                                <a href="javascript:void(0)" @click="toggleTab('FollowUser')">
                                    关注用户 11
                                </a>
                            </li>
                            <li :class="{active:currentTab == 'Fans'}">
                                <a href="javascript:void(0)" @click="toggleTab('Fans')">
                                    粉丝 1
                                </a>
                            </li>
                        </ul>
                        <div id="list-container">
                            <!--动态组件-->
                            <component :is="currentTab" keep-alive></component>
                        </div>
                    </div>
                    <div class="col-4 aside">
                        <div class="title">个人介绍</div>
                        <a class="function-btn"  href="javascript:void(0)" @click="showedit=true">
                            <i class="fa fa-pencil-square-o"></i> 编辑
                        </a>
                        <form action=""  v-if="showedit">
                                <textarea></textarea>
                                <input type="button" value="保存" class="btn btn-hollow" @click="showedit=false">
                                <a href="javacsript:void(0)" @click="showedit=false">取消</a>
                        </form>
                        <div class="description">
                            <div class="js-intro">
                                哈哈哈哈哈哈哈
                            </div>
                        </div>
                        <ul class="list user-dynamic">
                            <li>
                                <nuxt-link to="/users/123/collection">
                                    <i class="fa fa-th-large"></i>
                                    <span>他关注的专题/文集</span>
                                </nuxt-link>
                            </li>
                            <li>
                                <nuxt-link to="/users/123/like">
                                    <i class="fa fa-heart-o"></i>
                                    <span>他喜欢的文章</span>
                                </nuxt-link>
                            </li>
                        </ul>
                        <div>
                            <!--创建的专题-->
                            <div class="title">
                                他创建的专题
                            </div>
                            <nuxt-link to="/collection/new" target="_blank" class="function-btn new-collection-btn">
                                <i class="fa fa-plus"></i><span>新建专题</span>
                            </nuxt-link>
                            <ul class="list">
                                <li>
                                    <nuxt-link to="/collection/123" class="avatar-collection">
                                        <img src="~assets/img/movie.jpg">
                                    </nuxt-link>
                                    <nuxt-link to="/collection/123" class="name">
                                        grooooooter的专题
                                    </nuxt-link>
                                </li>
                            </ul>
                            <!--管理的专题-->
                            <div class="title">
                                他管理的专题
                            </div>
                            <ul class="list">
                                <li>
                                    <nuxt-link to="/collection/123" class="avatar-collection">
                                        <img src="~assets/img/movie.jpg">
                                    </nuxt-link>
                                    <nuxt-link to="/collection/123" class="name">
                                        grooooooter的专题
                                    </nuxt-link>
                                </li>
                            </ul>
                            <!--创建的文集-->
                            <div class="title">
                                他创建的文集
                            </div>
                            <ul class="list">
                                <li>
                                    <nuxt-link to="/note/123" class="avatar-collection">
                                        <i class="fa fa-book"></i>
                                    </nuxt-link>
                                    <nuxt-link to="/note/123" class="name">
                                        grooooooter的文集
                                    </nuxt-link>
                                </li>
                            </ul>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </template>
    <script>
        import myHeader from '~/components/myHeader'
        import FollowUser from '~/components/users/FollowUser'
        import Fans from '~/components/users/Fans'
        export default {
            name:'',
            data () {
                return {
                    currentTab:'FollowUser',
                    showedit:false,
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
            methods:{
                toggleTab:function(tab){
                    this.currentTab = tab;
                },
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
            components:{
                myHeader,FollowUser,Fans
               
            }
        }
    </script>
    <style>
    
    </style>