<template>
    <div>
        <div class="con" @click.stop="isshow=false">
            <div class="top">
                全部简信
            </div>
            <div class="user">
                <nuxt-link to="/m/123" class="avatar">
                    <img src="../../assets/img/default-avatar.jpg" alt="">
                </nuxt-link>
                <div class="in">
                    <div class="who">贾宝玉 
                        <div class="caozuo">
                            2017.09.16 06.52
                            <i class="fa fa-angle-down" @click.stop="isshow=!isshow"></i>
                        </div>
                    </div>
                    <div class="time"> 欢迎加入丰富多彩的原创内容社区——简书。有任何疑问（如何投稿，专题主编，签约作者，简叔，简小...</div>
                </div>
                
            </div>
            <div class="kuai" v-if="isshow">
                <ul>
                    <li>
                        <i class="fa fa-trash-o "></i>
                        删除会话
                    </li>
                    <li>
                        <i class="fa fa-frown-o "></i>
                        加入黑名单
                    </li>
                    <li>
                        <i class="fa fa-flag-o"></i>
                        举报用户
                    </li>
                </ul>
            </div>
        </div>
    </div>
</template>
<script>
    export default {
        name:'jianxin',
        components:{
            
        },
        data () {
            return {
                isshow:false,
            }
        },

    }
</script>
<style scoped>
 @media (min-width:992px){
    .con{
        margin-left: 280px;
    }
    
}

@media (max-width:1080px){
    .con{
        margin-left: 220px;
    }
    .in{
        width: 360px;
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
.user{
    padding: 20px 0 20px 20px;
    border-bottom: 1px solid #eaeaea;
    position: relative;
}
.user .avatar{
    width: 40px;
    height: 40px;
    border-radius: 50%;
    display: inline-block;
    vertical-align: middle;
    margin-right: 10px;
}
.user .in{
    display: inline-block;
    vertical-align: middle;
}
.user .in .who{
    font-size: 15px;
}
.user .in .time{
    font-size: 12px;
    color: #969696;
}
.user .neiron{
    margin: 10px 0;
}
.user .meta{
    font-size: 13px;
    color: #969696;
}
.user .meta i{
    font-size: 13px;
    margin: 0;
    margin-right: 5px;
}
.user .meta a{
    margin-right: 20px;
}
.user .meta a:hover{
    color: black !important;
}
.caozuo{
    float: right;
    font-size: 13px;
    color: #969696;
}
.caozuo i{
    cursor: pointer;
}
.kuai{
    position: absolute;
    top: 95px;
    right: 180px;
    background-color: #fff;
    z-index: 1000;
    border: 1px solid #eaeaea;
    box-shadow: 0 2px 8px rgba(0,0,0,.1);

}
.kuai ul li{
    padding: 5px 20px;
    font-size: 15;
    cursor: pointer;
}
.kuai ul li:hover{
    background-color: #eaeaea;
}
</style>