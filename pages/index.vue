<template>
    <div>
        <my-header></my-header>
        <div class="index my-container">
            <div class="row">
                <div class="col-8 main">
                    <!-- 轮播 -->
                    <div v-swiper:mySwiper="swiperOption" class="banner">
                        <div class="swiper-wrapper">
                            <div class="swiper-slide" v-for="banner in banners">
                                <img :src=banner>
                            </div>
                        </div>
                        <div class="swiper-pagination swiper-pagination-white"></div>
                        <div class="swiper-button-prev swiper-button-white"></div>
                        <div class="swiper-button-next swiper-button-white"></div>
                    </div>
                    <!-- 推荐专题 -->
                    <div class="recommend-collection">
                        <nuxt-link to="/collection/123">
                            <img src="../assets/img/index-img/tag-1.jpg" alt="">
                            <span>文学</span>
                        </nuxt-link>
                        <nuxt-link to="/collection/123">
                            <img src="../assets/img/index-img/tag-2.jpg" alt="">
                            <span>读书</span>
                        </nuxt-link>
                        <nuxt-link to="/collection/123">
                            <img src="../assets/img/index-img/tag-3.jpg" alt="">
                            <span>故事</span>
                        </nuxt-link>
                        <nuxt-link to="/collection/123">
                            <img src="../assets/img/index-img/tag-4.jpg" alt="">
                            <span>摄影</span>
                        </nuxt-link>
                        <nuxt-link to="/collection/123">
                            <img src="../assets/img/index-img/tag-5.jpg" alt="">
                            <span>电影</span>
                        </nuxt-link>
                        <nuxt-link to="/collection/123">
                            <img src="../assets/img/index-img/tag-6.jpg" alt="">
                            <span>IT·互联网</span>
                        </nuxt-link>
                        <nuxt-link to="/collection/123">
                            <img src="../assets/img/index-img/tag-7.jpg" alt="">
                            <span>人文社科</span>
                        </nuxt-link>
                        <nuxt-link class="more-hot-collection" to="/collection/123">
                            更多热门专题
                            <i class="fa fa-angle-right"></i>
                        </nuxt-link>
                    </div>
                    <!-- 横线 -->
                    <div class="split-line"></div>
                    <!-- 文章列表 -->
                    <div class="list-container">
                        <ul class="note-list">
                            <li class="have-img">
                                <nuxt-link class="wrap-img" to="/p/123">
                                    <img src="../assets/img/index-img/img-3.jpg" alt="">
                                </nuxt-link>
                                <div class="content">
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
                                        <nuxt-link to="/collection/123" class="collection-tag">
                                            短篇小说
                                        </nuxt-link>
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
                                    </div>
                                </div>
                            </li>
                        </ul>
                    </div>
                </div>
                <div class="col-4 aside">
                    <div class="board">
                        <nuxt-link to="/">
                            <img src="../assets/img/index-img/banner-1.png" alt="">
                        </nuxt-link>
                        <nuxt-link to="/">
                            <img src="../assets/img/index-img/banner-2.png" alt="">
                        </nuxt-link>
                        <nuxt-link to="/">
                            <img src="../assets/img/index-img/banner-3.png" alt="">
                        </nuxt-link>
                        <nuxt-link to="/">
                            <img src="../assets/img/index-img/banner-4.png" alt="">
                        </nuxt-link>
                        <nuxt-link to="/">
                            <img src="../assets/img/index-img/banner-5.png" alt="">
                        </nuxt-link>
                    </div>
                </div>
            </div>
        </div>

    </div>
</template>
<script>
    import myHeader from '../components/myHeader.vue'
    export default {
        components:{
            myHeader
        },
        data () {
            return {
                banners: [
                '/lunbo-1.jpg',
                '/lunbo-2.jpg',
                '/lunbo-3.jpg',
                '/lunbo-4.jpg',
                '/lunbo-5.jpg',
                ],
               swiperOption:{
                    autoplay:{
                    delay:3000,//切换时间
                    stopOnLastSlide:false,//是否停止在最后一张
                    disableOnInteraction:false,//禁止轮播
                    },
                    pagination:{
                        el:'.swiper-pagination'
                    },
                    navigation:{
                        nextEl:'.swiper-button-next',
                        prevEl:'.swiper-button-prev'
                    }
                    // some swiper options...
                }
            }
        },
        methods: {
                  
        },
        mounted() {
            
        }
        
    }
</script>
<style scoped>

</style>