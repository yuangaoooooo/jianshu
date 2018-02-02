<template>
    <div>
        <div id="comment-list" class="comment-list">
            <!-- 提交留言 -->
            <form class="new-comment">
                <nuxt-link class="avatar" to="/u/123">
                    <img src="../assets/img/default-avatar.jpg" alt="">
                </nuxt-link>
                <textarea  @focus="send=true"  placeholder="写下你的评论"
                    v-model="value"
                >

                </textarea>
                <transition name="fade">
                    <div v-if="send" class="write-function-block  clearfix">
                        <div class="emoji-modal-warp">
                            <a href="javascript:;" class="emoji" @click="showEmoji=!showEmoji">
                                <i class="fa fa-smile-o"></i>
                            </a>
                            <transition name="fade">
                                <div v-if="showEmoji" class="emoji-modal arrow-up">
                                    <!-- emoji组件 -->
                                    <vue-emoji @select="selectEmoji"></vue-emoji>
                                </div>
                            </transition>
                        </div>
                        <div class="hint">
                            Ctrl+Enter 发表
                        </div>
                        <a @click="sendData" class="btn btn-send" href="javascript:;">发送</a>
                        <a @click="send_one=false" class="cancel" href="javascript:void(0)">取消</a>
                    </div>
                </transition>
            </form>
            <!-- 留言列表 -->
            <div id="normal-comment-list" class="normal-comment-list">
                <!-- 留言的排序 -->
                <div class="top-title">
                    <span>3条评论</span>
                    <a href="JavaScript:;" class="author-only">
                        只看作者
                    </a>
                    <div class="pull-right">
                        <a class="active" href="JavaScript:;">
                            按喜欢排序
                        </a>
                        <a href="JavaScript:;">
                            按时间正序
                        </a>
                        <a href="JavaScript:;">
                            按时间倒序
                        </a>
                    </div>
                </div>
                <!-- 留言的正文 -->
                <!-- 加载效果 -->
                <div class="comment-placeholder">
                    <div class="author">
                        <div class="avatar"></div>
                        <div class="info">
                            <div class="name"></div>
                            <div class="meta"></div>
                        </div>    
                    </div>
                    <div class="title"></div>
                    <div class="title animated-delay"></div>
                    <div class="tool-group">
                        <i class="fa fa-thumbs-up"></i>
                        <div class="zan"></div>
                        <i class="fa fa-comment"></i>
                        <div class="zan"></div>
                    </div>
                </div>
                <!-- 留言 -->
                <div :id="'comment-'+comment.id" v-for="(comment,index) in comments"
                 class="comment">
                    <div class="comment-content">
                        <div class="author">
                            <nuxt-link class="avatar" to="/u/123">
                                <img :src="comment.user.avatar" alt="">
                            </nuxt-link>
                            <div class="info">
                                <nuxt-link class="name" to="/u/123">
                                    {{comment.user.nick_name}}
                                </nuxt-link>
                                <div class="meta">
                                    <span>
                                        {{comment.floor}}楼
                                        {{comment.create_at | time}}
                                    </span>
                                </div>
                            </div>
                        </div>
                        <div class="comment-warp">

                        </div>
                    </div>
                    <div class="sub-comment-list">

                    </div>
                </div>

            </div>
        </div>
    </div>
</template>
<script>
    import vueEmoji from '~/components/vueEmoji'
  
    export default {
        name:'myComment',
        data () {
            return {
                send:false,
                showEmoji:false,
                value:'',
                comments:[
                    {
                        id:19935725,
                        floor:2,
                        liked:true,
                        likes_count:20,
                        note_id:2054702,
                        user_id:6780849,
                        user:{
                            avatar:'/default-avatar.jpg',
                            id:6780849,
                            is_author:false,
                            nick_name:'南飞雨燕',
                            badgue:false,
                        },
                        create_at:"2018-01-25T05:54:25.000+08:00",
                        children_count:3,
                        compiled_content:"上阙景色单调，化用太多，味同嚼蜡",
                        children:[
                            {
                                id:20116563,
                                user_id:2604707,
                                user:{
                                    id:2604707,
                                    nick_name:'boom',
                                },
                                parent_id:19935725,
                                create_at:"2018-01-25T05:54:25.000+08:00",
                                compiled_content:"哈哈哈哈哈哈",
                            },
                            {
                                id:20113413,
                                user_id:2604708,
                                user:{
                                    id:2604708,
                                    nick_name:'huaxia',
                                },
                                parent_id:19935725,
                                create_at:"2018-01-25T05:54:25.000+08:00",
                                compiled_content:"六六六",
                            },
                            {
                                id:20113418,
                                user_id:2604709,
                                user:{
                                    id:2604709,
                                    nick_name:'阿斯蒂芬',
                                },
                                parent_id:19935725,
                                create_at:"2018-01-25T05:54:25.000+08:00",
                                compiled_content:"阿萨德感受到分公司的发给我",
                            },
                        ]
                    },
                    {
                        id:19935726,
                        floor:3,
                        liked:true,
                        likes_count:10,
                        note_id:2054702,
                        user_id:6784849,
                        user:{
                            avatar:'/default-avatar.jpg',
                            id:6784849,
                            is_author:false,
                            nick_name:'空间',
                            badgue:false,
                        },
                        create_at:"2018-01-25T05:56:25.000+08:00",
                        children_count:3,
                        compiled_content:"来看看",
                        children:[
                            {
                                id:20116563,
                                user_id:2604777,
                                user:{
                                    id:2604777,
                                    nick_name:'发v',
                                },
                                parent_id:19935726,
                                create_at:"2018-01-25T05:54:25.000+08:00",
                                compiled_content:"突然不是的",
                            },
                            {
                                id:20113413,
                                user_id:2604728,
                                user:{
                                    id:2604728,
                                    nick_name:'胜多负少的',
                                },
                                parent_id:19935726,
                                create_at:"2018-01-25T05:54:25.000+08:00",
                                compiled_content:"呢染头发",
                            },
                            {
                                id:20113418,
                                user_id:2604719,
                                user:{
                                    id:2604719,
                                    nick_name:'居然敢和你',
                                },
                                parent_id:19935726,
                                create_at:"2018-01-25T05:54:25.000+08:00",
                                compiled_content:"的积分工会那个号你电脑",
                            },
                        ]
                    },
                    {
                        id:19935727,
                        floor:4,
                        liked:true,
                        likes_count:1,
                        note_id:2054702,
                        user_id:6781849,
                        user:{
                            avatar:'/default-avatar.jpg',
                            id:6781849,
                            is_author:false,
                            nick_name:'吃辣的',
                            badgue:false,
                        },
                        create_at:"2018-01-25T07:54:25.000+08:00",
                        children_count:0,
                        compiled_content:"我的",
                        children:[
                        
                        ]
                    },
                ]  
            }
        },
        components:{
            vueEmoji
        },
        methods:{
            selectEmoji:function(code){
                this.showEmoji = false;
                this.value += code;
            },
            sendData:function(){
                console.log('发送value值数据给后端');
                
            }
        },
        filters: {
            time: function (value) {
                var d = new Date(value);
                var year = d.getFullYear();
                var month = d.getMonth() + 1;
                var day = d.getDate()<10 ? '0' + d.getDate() : '' + d.getDate();
                var hour = d.getHours();
                var minutes = d.getMinutes();
                var seconds = d.getSeconds();
                return  year+ '-' + month + '-' + day + ' ' + hour + ':' + minutes + ':' + seconds;
            }
        }
    }
</script>
<style scoped>
    .fade-enter-active,.fade-leave-active {
        opacity: 1;
        transition: .3s;
        -webkit-transition: .3s
    }
    .fade-enter,.fade-leave-to {
        opacity: 0;
        transform: translate3d(0,-5%,0);
        -webkit-transform: translate3d(0,-5%,0);
        transition: .3s;
        -webkit-transition: .3s
    }
   .note .post .comment-list{
       padding-top: 20px;
   } 
   .note .post .comment-list .new-comment{
       position: relative;
       margin-left: 48px;
       margin-bottom: 20px;
   }
   .note .post .comment-list .avatar{
       width: 38px;
       height: 38px;
       display: inline-block;
       margin-right: 5px;
   }
   .note .post .comment-list .new-comment .avatar{
       position: absolute;
       left: -48px;

   }
   .note .post .comment-list .new-comment textarea{
       width: 100%;
       height: 80px;
       padding-left: 10px 15px;
       border:1px solid #ccc;
       border-radius: 4px;
       display: inline-block;
       vertical-align: top;
       outline-style: none;
       resize: none;
       font-size: 13px;
       background: #f8f8f8;
   }
   .note .post .comment-list .new-comment .emoji-modal-warp{
    position: relative;
   }
   .note .post .comment-list .new-comment .emoji{
       float: left;
       margin-top: 14px;
   }
   .note .post .comment-list .new-comment .emoji i{
       font-size: 25px;
       color: #969696;
   }
   .note .post .comment-list .new-comment .emoji i:hover{
       color: #333 !important;
   }
   .note .post .comment-list .new-comment .hint{
       float: left;
       margin: 17px 0 0 20px;
       font-size: 13px;
       color: #969696;
   }
   .note .post .comment-list .new-comment .cancel{
       float: right;
       font-size: 16px;
       margin: 18px 30px 0 0;
       color: #969696 !important;
   }
   .note .post .comment-list .new-comment .cancel:hover{
       color: #2f2f2f !important;
   }
   .note .post .comment-list .new-comment .btn-send{
       float: right;
       width: 78px;
       padding: 8px 18px;
       margin: 10px 0;
       font-size: 18px;
       background: #42c02e;
       border-radius: 20px;
       color: #fff !important;
       box-shadow: none;
   }
   .note .post .comment-list .new-comment .btn-send:hover{
       background: #3db922;
   }
   .note .post .comment-list .new-comment .emoji-modal-warp .emoji-modal{
       position: absolute;
       top:50px;
       left: -48px;
       width: 402px;
       height: 208px;
       padding: 10px;
       background: #fff;
       border: 1px solid #d9d9d9;
       border-radius: 4px;
       box-shadow: 0 5px 25px rgba(0, 0, 0, 0.1)
   }
   .arrow-up:after{
       width: 15px;
       height: 15px;
       content: '';
       display: inline-block;
       border-left: 1px solid #d9d9d9;
       border-top: 1px solid #d9d9d9;
       background: #fff;
       position: absolute;
       left: 50px;
       top:-1px;
       transform: translate3d(0,-50%,0) rotate(45deg);
   }

   .note .post .comment-list .normal-comment-list{
       margin-top: 30px;
   }
   .note .post .comment-list .top-title{
       padding-bottom: 20px; 
       border-bottom: 1px solid #f0f0f0;
   }
   .note .post .comment-list .top-title span{
       font-size: 17px;
       font-weight: 700;
   }
   .note .post .comment-list .top-title .author-only{
        font-size: 12px;
        padding: 4px 8px;
        border: 1px solid #e1e1e1;
        border-radius: 12px;
        color: #969696 !important;
        margin-left: 10px;
   }
   .note .post .comment-list .top-title .pull-right a{
        margin-left: 10px;
        font-size: 12px;
        color: #969696 !important;
   }
   .note .post .comment-list .top-title .pull-right a.active{
        color: #2f2f2f !important;
   }
   .note .post .comment-list .comment{
       padding: 20px 0 30px 0;
       border: 1px solid #f0f0f0;
   }
   .note .post .comment-list .comment .info{
        display: inline-block;
        vertical-align: middle;
   }
   .note .post .comment-list .comment .info .name{
       font-size: 15px;
   }
   .note .post .comment-list .comment .info .meta{
       font-size: 12px;
       color: #969696 !important;
   }
</style>