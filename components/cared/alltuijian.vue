<template>
    <div>
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
                    <img src="~/assets/img/default-avatar.jpg" alt="">
                </nuxt-link>
                <a class="btn btn-success" href="javascript:void(0)":class="followObj"
                @click="isFollow" @mouseover="noFollow" @mouseleave="beFollow">
                    <i class="fa" :class="iconObj" ref="icon"></i>
                    <span ref="followWord" >关注</span>
                </a>
                <nuxt-link class="title" to="/u/123">
                    宋小宝
                </nuxt-link>
                <p>
                    <span class="lan">简书</span>
                    收录了265305篇文章，198520人关注
                    <p><span class="lan">grooooooter</span> 关注了作者</p>
                </p>
            </div>
        </div>
    </div>
</template>
<script>
    export default {
        name:'alltuijian',
        data () {
            return {
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
}
.content-guanzhu .title{
    font-size: 15px;
    line-height: 1.8;
    font-weight: 700;
    color: #333;
    margin-right: 5px;
}
    .content-guanzhu .info{
    margin-bottom: 20px;
}
    .content-guanzhu .info img{
    border-radius: 50%;
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
.lan{
    color: #3194d0;
}
</style>