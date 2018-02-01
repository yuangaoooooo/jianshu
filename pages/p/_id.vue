<template>
    <div @click.stop="listShow=false">
        <my-header></my-header>
        <div class="note">
            <!-- 文章区域 -->
            <div class="post">
                <!-- 正文 -->
                <div class="article">
                    <h1 class="title">《解语花-池鳞弄月》</h1>
                    <div class="author">
                        <nuxt-link class="avatar" to="/u/123">
                            <img src="~/assets/img/default-avatar.jpg" alt="">
                        </nuxt-link>
                        <div class="info">
                            <span class="name">一筐猪</span>
                            <a class="btn-sm" href="javascript:void(0)" :class="followObj"
                             @click="isFollow" @mouseover="noFollow" @mouseleave="beFollow">
                                <i class="fa" :class="iconObj" ref="icon"></i>
                                <span ref="followWord">关注</span>
                            </a>
                            <div class="meta">
                                <span>2018.01.23 16:09</span>
                                <span>字数2273</span>
                                <span>阅读889</span>
                                <span>评论8</span>
                                <span>喜欢36</span>
                            </div>
                        </div>
                    </div>
                    <div class="show-content">
                        <p>池鳞弄月，瓦兽含烟，风逐叶摇曳。玉波交继。凭香砌、露浸台阶寒屣。怦然心悸。凝望眼、清辉素壁。空寂寥、遍倚阑干，远梦人千里。<br></p>
                        <p>长恨仗酒狂恣。纵泛萍浪迹，少年狭气。几番相戏。不禁情、甚是韶华骄肆。今朝省计。伤流景、为余叹息。念昔年、竹马青梅，泪与牛山涕。</p>
                    </div> 
                    <!--  -->
                    <div class="show-foot">
                        <nuxt-link class="notebook" to="/nb/123">
                            <i class="fa fa-book"></i>
                            <span>我的文集</span>           
                        </nuxt-link>
                        <div class="copyright">
                            &copy; 著作权归作者所有
                        </div>
                    </div>
                    <!-- 作者信息 -->
                    <div class="follow-detail">
                        <div class="info">
                            <nuxt-link class="avatar" to="/u/123">
                                <img src="../../assets/img/default-avatar.jpg" alt="">
                            </nuxt-link>
                            <a class="btn btn-success" href="javascript:void(0)":class="followObj"
                            @click="isFollow" @mouseover="noFollow" @mouseleave="beFollow">
                                <i class="fa" :class="iconObj" ref="icon2"></i>
                                <span ref="followWord2" >关注</span>
                            </a>
                            <nuxt-link class="title" to="/u/123">
                                一筐猪
                            </nuxt-link>
                            <i class="fa fa-mars"></i>
                            <p>
                                写了 53260 字，被 1480 人关注，获得了 31757 个喜欢
                            </p>
                        </div>
                        <div class="signature">
                            为城市里的不安和孤独发声
                        </div>
                    </div>
                    <!-- 喜欢 分享 -->
                    <div class="meta-bottom">
                        <div class="like">
                            <div class="btn like-group" :class="{active:active_like}">
                                <div class="btn-like" @click="isLike">
                                    <a href="javascript:void(0)">
                                        <i class="fa fa-heart-o"></i>
                                        <span>喜欢</span>
                                    </a>
                                </div>
                                <div class="modal-wrap">
                                    <a href="javascript:void(0)">{{like_number}}</a>
                                </div>
                            </div>
                        </div>
                        <div class="share-group">
                            <a href="javascript:void(0)"
                            b-btn  v-b-tooltip.hover  title = "分享到微博">
                                <i class="fa fa-weibo weibo"></i>
                            </a>
                            <a href="javascript:void(0)"
                            b-btn  v-b-tooltip.hover  title = "分享到微信">
                                <i class="fa fa-weixin weixin"></i>
                            </a>
                            <a href="javascript:void(0)"
                            b-btn  v-b-tooltip.hover  title = "分享到QQ">
                                <i class="fa fa-qq qq"></i>
                            </a>
                            <a class="more-share" href="javascript:void(0)" @click.stop="listShow=true">
                                更多分享
                                <ul class="share-list" v-show="listShow">
                                    <li>
                                        <i class="fa fa-star qqkj"></i> 
                                        <span>分享到QQ空间</span>
                                    </li>
                                    <li>
                                        <i class="fa fa-twitter twitter"></i>
                                        <span>分享到Twitter</span>
                                    </li>
                                    <li>
                                        <i class="fa fa-facebook-official facebook"></i>
                                        <span>分享到FaceBook</span>
                                    </li>
                                    <li>
                                        <i class="fa fa-google-plus google"></i>
                                        <span>分享到Google+</span>
                                    </li>
                                    <li>
                                        <i class="fa fa-snowflake-o douban"></i>
                                        <span>分享到豆瓣</span>
                                    </li>
                                    <img class="sanjiao" src="../../assets/img/sanjiao.png" alt="">
                                </ul>
                            </a>
                        </div>
                    </div>
                </div>
                <!-- 回复组件 -->
                <my-comment></my-comment>
                
            </div>
            <!-- 悬浮的操作框 -->
            <div class="side-bar"></div>
            <!-- 对应的推荐阅读 -->
            <div class="note-bottom"></div>
        </div>
    </div>
</template>
<script>
    import myHeader from '../../components/myHeader.vue'
    import myComment from '../../components/myComment.vue'
    export default {
        name:'',
        data () {
            return {
                followObj:{
                    'follow':true,
                    'following':false
                },
                iconObj:{
                    'fa-plus-square-o':true,
                    'fa-check':false
                },
                active_like:false,
                like_number:108,
                listShow:false
            }
        },
        components:{
            myHeader,myComment
        },
        methods:{
            isFollow:function(){
                let word = this.$refs.followWord.innerHTML;
                // 这里预留关注的ajax操作
                this.followObj.follow = !this.followObj.follow;
                this.followObj.following = !this.followObj.following;
                this.iconObj['fa-plus-square-o'] = !this.iconObj['fa-plus-square-o'];
                this.iconObj['fa-check'] = !this.iconObj['fa-check'];
                
                this.$refs.followWord.innerHTML = word == '关注' ? '已关注' : '关注';
                this.$refs.followWord2.innerHTML = word == '关注' ? '已关注' : '关注';
            },
            noFollow:function(){
                let word = this.$refs.followWord.innerHTML;
                if(word == '已关注'){
                    this.$refs.followWord.innerHTML = '取消关注';
                    this.$refs.icon.className = 'fa fa-close';

                    this.$refs.followWord2.innerHTML = '取消关注';
                    this.$refs.icon2.className = 'fa fa-close';
                }
            },
            beFollow:function(){
                let word = this.$refs.followWord.innerHTML;
                if(word == '取消关注'){
                    this.$refs.followWord.innerHTML = '已关注';
                    this.$refs.icon.className = 'fa fa-check';

                    this.$refs.followWord2.innerHTML = '已关注';
                    this.$refs.icon2.className = 'fa fa-check';
                }
            },
            isLike:function(){
                this.active_like = !this.active_like;
                if(this.active_like == true){
                    ++this.like_number;
                }else{
                    --this.like_number;
                }    
                //将最新的like_number 值传到数据库
            }
        }
    }
</script>
