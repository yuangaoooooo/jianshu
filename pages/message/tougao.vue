<template>
    <div>
        <div class="con">
            <div class="top">全部投稿请求</div>
            <ul>
                <li>
                    <a class="all" href="javascipt:;">
                        <div><i class="fa fa-upload"></i></div>
                        全部未处理请求
                    </a>
                </li>
                <li>
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
                            <nuxt-link class="title" to="/u/123">
                                grooooooter
                            </nuxt-link>
                            <p>
                                还有一个请求未处理
                            </p>
                        </div>
                    </div>
                </li>
            </ul>
        </div>
        
    </div>
</template>
<script>
    export default {
        name:'tougao',
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
ul li{
    border-bottom: 1px solid #eaeaea;
}
.all{
    display: inline-block;
    padding-left: 20px;
    margin-bottom: 20px;
    font-size: 15px;
}
.all div{
    width: 48px;
    height: 48px;
    text-align: center;
    line-height: 48px;
    border: 1px #eaeaea solid;
    border-radius: 5px;
    display: inline-block;
    margin-right: 20px;
}
.all div i{
    color: #ea6f5a;
    font-size: 22px;
}
.content-placeholder-guanzhu{
    padding-left: 20px;
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
.content-guanzhu{
    margin-top: 20px;
    padding-left: 20px;
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
.content-guanzhu .avatar img{
    border-radius: 5px;
}
 .content-guanzhu .title{
    font-size: 15px;
    line-height: 1.8;
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