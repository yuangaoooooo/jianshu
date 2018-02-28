<template>
    <div>
        <div id="comment-list" class="comment-list">
            <!-- 一级提交留言表单 -->
            <form class="new-comment">
                <nuxt-link class="avatar" to="/u/123">
                    <img src="../assets/img/default-avatar.jpg" alt="">
                </nuxt-link>
                <textarea  @focus="send=true"  placeholder="写下你的评论"
                    v-model="commentData"
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
                        <a @click="send=false" class="cancel" href="javascript:void(0)">取消</a>
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
                    <!-- 一级回复内容 -->
                    <div class="comment-content">
                        <div class="author">
                            <nuxt-link class="avatar" to="/u/123">
                                <img :src="comment.user.avatar" alt="" :id="'user_popover-'+comment.id" variant="primary">
                            </nuxt-link>
                            <b-popover :target="'user_popover-'+comment.id" placement="top" triggers="hover">
                                <div class="user_popover">
                                    <nuxt-link class="avatar" to="/u/123">
                                        <img :src="comment.user.avatar" alt="">
                                    </nuxt-link>
                                    <div class="info">
                                        <nuxt-link class="name" to="/u/123">
                                            {{comment.user.nick_name}}
                                        </nuxt-link>
                                        <div class="meta">
                                            <span>
                                              爱上的卡夫卡来阿里速度快
                                            </span>
                                        </div>    
                                    </div>
                                    <div class="pop_foot">
                                        <div>
                                            
                                        </div>
                                        <div class="btn btn-success guanzhu">
                                                关注
                                        </div>
                                        <div class="btn btn-success cancel">
                                            取消
                                        </div>
                                        
                                    </div>
                                </div>
                            </b-popover>


                            <div class="info">
                                <nuxt-link class="name" to="/u/123">
                                    {{comment.user.nick_name}}
                                </nuxt-link>
                                <div class="meta">
                                    <span>
                                        {{comment.floor}}楼
                                        {{comment.create_at | formatDate}}
                                    </span>
                                </div>
                            </div>
                        </div>
                        <div class="comment-warp">
                            <p>{{comment.compiled_content}}</p>
                            <div class="tool-group">
                                <a href="javascript:;" class="zan">
                                    <i class="fa fa-thumbs-o-up"></i>
                                    <span>{{comment.likes_count}}人点赞</span>
                                </a>
                                <a href="javascript:;"  @click="showSubCommentForm(index,'top','')">
                                    <i class="fa fa-comment-o"></i>
                                    <span>回复</span>
                                </a>
                            </div>
                        </div>
                    </div>
                    <!-- 二级回复 -->
                    <div v-if="comment.children.length != 0" class="sub-comment-list">
                        <div v-for="(subComment,nindex) in comment.children" :id="'comment-'+subComment.id" class="sub-comment">
                            <p>
                                <nuxt-link to="/u/123">
                                    {{subComment.user.nick_name}}     
                                </nuxt-link>
                                :
                                <span v-html="subComment.compiled_content">
                               
                                </span>
                            </p>
                            <div class="sub-tool-group">
                                <span>{{subComment.create_at | formatDate}}</span>
                                <a href="javascript:;"  @click="showSubCommentForm(index,subComment.id,subComment.user.nick_name)">
                                    <i class="fa fa-comment-o"></i>
                                    <span>回复</span>
                                </a>
                            </div>
                        </div>
                        <div class="more-comment">
                            <a class="add-comment-btn" href="javascript:;" @click="showSubCommentForm(index,'bottom','')">
                                <i class="fa fa-pencil"></i>
                                <span>添加新评论</span>
                            </a>
                        </div>
                    </div>
                    <!-- 二级回复表单 -->
                    <transition :duration="200" name="fade">
                        <form v-if="activeIndex.includes(index)"  class="second-comment" >
                            <textarea v-focus  placeholder="写下你的评论" ref="content"
                                v-model="subCommentList[index]" 
                            >
                            </textarea>
                            <transition name="fade">
                                <div class="write-function-block  clearfix">
                                    <div class="emoji-modal-warp">
                                        <a href="javascript:;" class="emoji" @click="showSubEmoji(index)">
                                            <i class="fa fa-smile-o"></i>
                                        </a>
                                        <transition :duration="200" name="fade">
                                            <div v-if="emojiIndex.includes(index)" class="emoji-modal arrow-up">
                                                <!-- emoji组件 -->
                                                <vue-emoji :index="index" ref="emoji" @select="selectSubEmoji"></vue-emoji>
                                            </div>
                                        </transition>
                                    </div>
                                    <div class="hint">
                                        Ctrl+Enter 发表
                                    </div>
                                    <a @click="sendSubCommentData(index)" class="btn btn-send" href="javascript:;">发送</a>
                                    <a @click="closeSubComment(index)" class="cancel" href="javascript:void(0)">取消</a>
                                </div>
                            </transition>
                        </form>
                    </transition>
                </div>

            </div>
        </div>
    </div>
</template>
<script>
    import Vue from 'vue'
    import vueEmoji from '~/components/vueEmoji'
    export default {
        name:'myComment',
        data () {
            return {
                send:false,
                showEmoji:false,
                commentData:'',
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
                                create_at:"2018-01-26T06:54:25.000+08:00",
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
                                create_at:"2018-01-29T05:59:25.000+08:00",
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
                                create_at:"2018-01-30T05:54:25.000+08:00",
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
                        create_at:"2018-01-26T08:56:25.000+08:00",
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
                                create_at:"2018-01-27T07:54:25.000+08:00",
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
                                create_at:"2018-01-27T09:54:25.000+08:00",
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
                                create_at:"2018-01-28T01:54:25.000+08:00",
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
                        create_at:"2018-01-31T06:24:05.000+08:00",
                        children_count:0,
                        compiled_content:"我的阿萨德阿萨德法师是的父亲发v的看见爱上阿萨德法师是的父亲发v的看见爱上阿萨德法师是的父亲发v的看见爱上法师是的父亲发v的看见爱上的合法化是的罚款是的空间阿萨德科技",
                        children:[
                        
                        ]
                    },
                    {
                        id:19935728, 
                        floor:5,
                        liked:true,
                        likes_count:5,
                        note_id:2054702,
                        user_id:1781849,
                        user:{
                            avatar:'/default-avatar.jpg',
                            id:1781849,
                            is_author:false,
                            nick_name:'gy',
                            badgue:false,
                        },
                        create_at:"2018-01-31T01:24:05.000+08:00",
                        children_count:0,
                        compiled_content:"时间对吗？时间对吗？时间对吗？时间对吗？",
                        children:[
                        
                        ]
                    },
                ],
                activeIndex:[],
                emojiIndex:[],
                subCommentList:[],
                commentFormState:[],
                commentId:[],
            }
        },
        components:{
            vueEmoji
        },
        directives: {
            "focus":{
                 // 钩子函数：bind inserted update componentUpdated unbind
                 // 钩子函数的参数：el，binding，vnode，oldVnode
                bind:function(el,binding,vnode,oldVnode){
                    //console.log(el);
                    el.focus();
                },
                inserted:function(el){
                    el.focus();
                }
            }  
        },
        methods:{
            selectEmoji:function(code){
                this.showEmoji = false;
                this.commentData += code;
            },
            sendData:function(){
                console.log('发送value值数据给后端');     
            },   
            showSubCommentForm:function(index,id,name){
                let ID = id.toString();
               if(this.commentId[index] == ID){
                   //点两次
                   this.activeIndex.splice(this.activeIndex.indexOf(index),1);
                   this.commentId[index] = '';
               }else{
                   //点一次
                   //清除表单内容
                   this.subCommentList[index] = '';
                   //表情关掉
                   this.emojiIndex = [];
                   if(!this.activeIndex.includes(index)){
                       this.activeIndex.push(index);
                   }
                   // 判断用户名是否存在，如果存在添加
                   if(name != ''){
                       this.subCommentList[index] = `@${name} `;
                   }
                   //存一下上一个回复列表对应点击的按钮
                   this.commentId[index] = ID;
               }
            },
            
            sendSubCommentData:function(value){
                let index = this.activeIndex.indexOf(value);
                this.activeIndex.splice(index,1);
                // value是下标
                alert(this.subCommentList[value]);
            },
            closeSubComment:function(value){
                this.activeIndex.splice(index = this.activeIndex.indexOf(value),1);    
            },
            showSubEmoji:function(value){
                if(this.emojiIndex.includes(value)){
                    let index = this.emojiIndex.indexOf(value);
                    this.emojiIndex.splice(index,1);
                    this.emojiIndex = [];
                }else{
                    this.emojiIndex = [];
                    this.emojiIndex.push(value);
                }
            },
            selectSubEmoji:function(code){
                // console.log(code);
                //console.log(this.emojiIndex[0]);
                
                // 当前下标
                let index = this.emojiIndex[0];
                // 将表情所代表的code值放入表单中
                if(this.subCommentList[index] == null){
                    this.subCommentList[index] = '';
                }
                this.subCommentList[index] +=code;
                //关掉emoji框
                this.emojiIndex = [];
                //聚焦一下
                let num = this.activeIndex.indexOf(index);
                this.$refs.content[num].focus();
                
            },
        },
       
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
       border-top: 1px solid #f0f0f0;
       border-bottom: 1px solid #f0f0f0;
   }
   .note .post .comment-list .comment .author{
       margin-bottom: 15px;
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
   /* 用户头像提示 */
   .user_popover{

   }
   .user_popover .avatar{
       display: inline-block;
       vertical-align: middle;
       margin-right: 5px;
   }
   .user_popover .info{
        display: inline-block;
       vertical-align: middle;
   }
   .user_popover .info .name{
       font-size: 15px;
       font-weight: 700;
   }
   .user_popover .info .meta{
       font-size: 13px;
   }
   .pop_foot{
       border-top: 1px #ccc solid;
       padding: 20px 0;
   }
   .pop_foot .cancel{
       float: right;
   }
   .pop_foot .guanzhu{
       float: right;
       margin-right: 10px;
   }


   .note .post .comment-list .comment .comment-warp p{
        font-size: 16px;
        margin: 10px 0;
        line-height: 1.5;
        word-break: break-all !important;
   }
   .note .post .comment-list .comment .comment-warp .tool-group .zan.active i{
        color: #ea6f5a;
   }
   .note .post .comment-list .comment .comment-warp .tool-group .zan.active span{
       color: #2f2f2f !important;
   }
   .note .post .comment-list .comment .comment-warp .tool-group a{
       color: #969696 !important;
       margin-right: 10px;
   }
   .note .post .comment-list .comment .comment-warp .tool-group a i{
       font-size: 18px;
       margin-right: 5px;
   }
   .note .post .comment-list .comment .comment-warp .tool-group a span{
       font-size: 14px;
   }
   .note .post .comment-list .sub-comment-list{
       border-left: 2px solid #d9d9d9;
       margin-top: 10px;
       padding: 5px 0 5px 20px;
   }
   .note .post .comment-list .sub-comment-list .sub-comment{
       padding-bottom: 15px;
       margin-bottom: 15px;
       border-bottom: 1px dashed #f0f0f0;
   }
   .note .post .comment-list .sub-comment-list .sub-comment p{
       font-size: 14px;
       line-height: 1.5;
       margin-bottom: 5px;
   }
   .note .post .comment-list .sub-comment-list .sub-comment p a{
       color: #3194d0 !important;
   }
   .note .post .comment-list .sub-comment-list .sub-comment .sub-tool-group{
        font-size: 12px;
        color: #969696;
   }
   .note .post .comment-list .sub-comment-list .sub-comment .sub-tool-group a{
       margin-left: 5px;
   }
   .note .post .comment-list .sub-comment-list .sub-comment .sub-tool-group a i{
       margin-right: 5px;
   }
   .note .post .comment-list .sub-comment-list .more-comment{
       font-size: 14px;
       color: #969696;
   }
   .note .post .comment-list .sub-comment-list .more-comment a:hover{
       color: #2f2f2f !important;
   }
   .note .post .comment-list .sub-comment-list .more-comment a i{
       margin-right: 5px;
   }
   /* 二级回复表单样式 */
   .note .post .comment-list .comment .second-comment{
        border-left: 2px solid #d9d9d9;
       padding: 15px 0 5px 20px;
   }
   .note .post .comment-list .comment .second-comment textarea{
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
       background: #f8f8f8
   }
   .note .post .comment-list .comment .second-comment .emoji-modal-warp{
    position: relative;
   }
   .note .post .comment-list .comment .second-comment .emoji{
       float: left;
       margin-top: 14px;
   }
   .note .post .comment-list .comment .second-comment .emoji i{
       font-size: 25px;
       color: #969696;
   }
   .note .post .comment-list .comment .second-comment i:hover{
       color: #333 !important;
   }
   .note .post .comment-list .comment .second-comment .hint{
       float: left;
       margin: 17px 0 0 20px;
       font-size: 13px;
       color: #969696;
   }
   .note .post .comment-list .comment .second-comment .cancel{
       float: right;
       font-size: 16px;
       margin: 18px 30px 0 0;
       color: #969696 !important;
   }
   .note .post .comment-list .comment .second-comment .cancel:hover{
       color: #2f2f2f !important;
   }
   .note .post .comment-list .comment .second-comment .btn-send{
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
   .note .post .comment-list .comment .second-comment .btn-send:hover{
       background: #3db922;
   }
   .note .post .comment-list .comment .second-comment .emoji-modal-warp .emoji-modal{
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
   
</style>