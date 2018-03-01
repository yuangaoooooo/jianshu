<template>
    <div>
        <div class="con">
            <div class="top">
                收到的评论
            </div>
            <div class="con-placeholder">
                <div class="avatar"></div>
                <div class="use">
                    <p class="name"></p>
                    <p class="time"></p>
                </div>
                <div class="neiron"></div>
                <div class="meta">
                    <i class="fa fa-comment-o"></i>
                    <div href="javascript:;"></div>
                    <i class="fa fa-share"></i>
                    <div href="javascript:;"></div>
                </div>
            </div>
            <div class="user">
                <nuxt-link to="/m/123" class="avatar">
                    <img src="../../assets/img/default-avatar.jpg" alt="">
                </nuxt-link>
                <div class="in">
                    <div class="who">a23546wd 评论了你的文章<span class="lan">《2018-02-09》</span></div>
                    <div class="time">2018.02.10 08:26</div>
                </div>
                <div class="neiron">
                    guonianhao
                </div>
                <div class="meta">
                    <i class="fa fa-comment-o"></i>
                    <a href="javascript:;">回复</a>
                    <i class="fa fa-share"></i>
                    <a href="javascript:;">查看对话</a>
                </div>
            </div>
        </div>            
    </div>
</template>
<script>
    export default {
        name:'pinlun',
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
    .in{
        width: 360px;
    }
} 
.con-placeholder {
    padding: 10px 0 20px 20px;
}
.con-placeholder .avatar{
    display: inline-block;
    vertical-align: middle;
    width: 40px;
    height: 40px;
    border-radius: 50%;
    background-color: #eaeaea;
}
.con-placeholder .use{
    display: inline-block;
    vertical-align: middle;
    padding-left: 5px;
}
.con-placeholder .use .name{
    display: block;
    width: 300px;
    height: 18px;
    background-color: #eaeaea;
    margin: 0;
    animation: loading 1s ease-in-out infinite;
}
.con-placeholder .use .time{
    display: block;
    width: 100px;
    height: 16px;
    background-color: #eaeaea;
    margin: 0;
    margin-top: 3px;
    animation: loading2 1s ease-in-out -.5s infinite;
}
.con-placeholder .neiron{
    width: 200px;
    height: 20px;
    background-color: #eaeaea;
    margin: 10px 0;
    animation: loading2 1s ease-in-out infinite;

}
.con-placeholder .meta{
    color: #eaeaea;
}
.con-placeholder .meta div{
    width: 30px;
    height: 16px;
    background-color: #eaeaea;
    display: inline-block;
    margin: 0 5px;
}
@keyframes loading{
    0%{
        width: 150px;
    }
    25%{
        width: 300px;
    }
    50%{
        width: 300px;
    }
    100%{
        width: 150px;
    }
}
@keyframes loading2{
    0%{
        width: 50px;
    }
    25%{
        width: 100px;
    }
    50%{
        width: 100px;
    }
    100%{
        width: 50px;
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
    padding: 10px 0 20px 20px;
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
.lan{
    color: blue;
}
</style>