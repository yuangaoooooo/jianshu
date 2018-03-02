<template>
    <div>
        <my-header></my-header>
        <div class="main">
            <div class="aside">
                <ul>
                    <li  :class="{isActive:this.$route.path=='/message/pinlun'}">
                        <nuxt-link to="/message/pinlun">
                            <i class="fa fa-comment-o"></i>评论
                        </nuxt-link>
                    </li>
                    <li :class="{isActive:this.$route.path=='/message/jianxin'}">
                        <nuxt-link to="/message/jianxin">
                            <i class="fa fa-envelope-open-o"></i>简信
                        </nuxt-link>
                    </li>
                    <li :class="{isActive:this.$route.path=='/message/tougao'}">
                        <nuxt-link to="/message/tougao">
                            <i class="fa fa-hand-o-up"></i>投稿请求
                        </nuxt-link>
                    </li>
                    <li :class="{isActive:this.$route.path=='/message/likezan'}">
                        <nuxt-link to="/message/likezan">
                            <i class="fa fa-heart-o"></i>喜欢和赞
                        </nuxt-link>
                    </li>
                    <li :class="{isActive:this.$route.path=='/message/guanzhu'}">
                        <nuxt-link to="/message/guanzhu">
                            <i class="fa fa-user-o "></i>关注
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
        name:'message',
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
        width: 280px;
    }
    
}

@media (max-width:1080px){
    .main {
        width: 750px;
    }
    .aside{
        width: 220px;
    }
}   
.main{
    margin: 0 auto;
    padding-top: 30px;
    position: relative;
}
.aside{
    position: absolute;
    top: 40px;
}
.aside ul a{
    height: auto;
    padding: 10px 25px;
    line-height: 30px;
    display: block;
}
.aside ul li{
    border-radius: 4px;
    font-size: 15px;
}
.aside ul li i{
    font-size: 20px;
}
.aside ul li:hover{
    background-color: #f0f0f0;
}
.aside ul a i{
    color: #ea6f5a;
    margin-right: 20px;
}
nuxt-child{
    float: right;
}
.isActive{
    background-color: #f0f0f0;
}
</style>