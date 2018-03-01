<template>
    <div>
        <div class="con">
            <div class="top">收到的喜欢和赞</div>
            <div class="content-placeholder-guanzhu">
                <div class="avatar"></div>
                <div class="title">
                    <div class="name"></div>
                    <div class="jianjie"></div>
                </div>
            </div>
            <div class="content-guanzhu">
                <div class="info">
                    <nuxt-link class="avatar" to="/u/123">
                        <img src="../../assets/img/default-avatar.jpg" alt="">
                    </nuxt-link>
                    <div class="jianjie">
                        <nuxt-link class="title" to="/u/123">
                            grooooooter 喜欢了你的文章<span class="lan">《起风了》</span>
                        </nuxt-link>
                        <p>
                            2017.02.09 09.36
                        </p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
    export default {
        name:'likezan',
        components:{
            
        },
        data () {
            return {
                
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
    padding: 10px 0 0 20px;
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
.content-guanzhu{
    border-bottom: 1px solid #ccc;
    margin-top: 20px;
    padding: 10px 0 10px 20px;
}

.content-guanzhu .following{
    background: none;
}

.content-guanzhu .avatar {
    width: 40px;
    height: 40px;
    margin-right: 10px;
    border-radius: 50%;
    display: inline-block;
    vertical-align: middle;
}
.content-guanzhu .jianjie{
    display: inline-block;
    vertical-align: middle;
}
 .content-guanzhu .title{
    font-size: 15px;
    line-height: 1.8;
    margin-right: 5px;
}
.lan{
    color: #3194d0;
}
.content-guanzhu .info{
    margin-bottom: 20px;
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