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
            <div  :id="'comment-'+comment.id" v-for="(comment,index) in comments">
                <div class="user">
                    <nuxt-link to="/m/123" class="avatar">
                        <img src="../../assets/img/default-avatar.jpg" alt="">
                    </nuxt-link>
                    <div class="in">
                        <div class="who">{{comment.user.nick_name}}评论了你的文章<span class="lan">《2018-02-09》</span></div>
                        <div class="time">{{comment.create_at | formatDate}}</div>
                    </div>
                    <div class="neiron">
                        {{comment.compiled_content}}
                    </div>
                    <div class="meta">
                        <i class="fa fa-comment-o"></i>
                        <a href="javascript:;" @click="showSubCommentForm(index,comment.user.nick_name)">回复</a>
                        <i class="fa fa-share"></i>
                        <a href="javascript:;">查看对话</a>
                    </div>
                </div>
                <!-- 回复表单 -->
                <transition :duration="200" name="fade">
                    <form v-if="activeIndex.includes(index)"  class="second-comment" >
                        <textarea v-focus="commentFormState[index]" @blur="commentFormState[index]=false"  placeholder="写下你的评论" ref="content"
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
</template>
<script>
    import Vue from 'vue'
    import vueEmoji from '~/components/vueEmoji'
    export default {
        name:'pinlun',
        components:{
           vueEmoji
        },
        data () {
            return {
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
         directives: {
            "focus":{
                 // 钩子函数：bind inserted update componentUpdated unbind
                 // 钩子函数的参数：el，binding，vnode，oldVnode
                bind:function(el,{value}){
                    //console.log(el);
                    if(value){
                        el.focus();
                    }
                },
                update:function(el,{value}){
                    if(value){
                        el.focus();
                    }
                },
                inserted:function(el,{value}){
                    if(value){
                        el.focus();
                    }
                }
            }  
        },
        methods:{
            showSubCommentForm:function(index,name){ 
                if(!this.activeIndex.includes(index)){
                    this.activeIndex.push(index);
                    // 判断用户名是否存在，如果存在添加
                    if(name != ''){
                        this.subCommentList[index] = `@${name} `;
                    }

                    //存一下上一个回复列表对应点击的按钮
                    //获取焦点
                    this.commentFormState[index]=true;
                    //记录index
                    this.commentId[index] = index;
                }else{
                    this.activeIndex.splice(this.activeIndex.indexOf(index),1); 
                    this.emojiIndex = [];   
                    this.subCommentList[index] = '';
                    this.commentId = [];
                    
                }

            },
            
            sendSubCommentData:function(value){
                let index = this.activeIndex.indexOf(value);
                this.activeIndex.splice(index,1);
                // value是下标
                alert(this.subCommentList[value]);
                this.subCommentList[value] = '';
                this.commentId = [];
            },
            closeSubComment:function(value){
                this.activeIndex.splice(this.activeIndex.indexOf(value),1);    
                this.subCommentList[value] = '';
                this.commentId = [];
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
                this.commentFormState[index]=true;  
            },
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
    width: 150px;
    height: 20px;
    background-color: #eaeaea;
    margin: 10px 0;
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
.second-comment{
        border-left: 2px solid #d9d9d9;
       padding: 15px 0 5px 20px;
   }
.second-comment textarea{
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
.second-comment .emoji-modal-warp{
    position: relative;
   }
 .second-comment .emoji{
       float: left;
       margin-top: 14px;
   }
.second-comment .emoji i{
       font-size: 25px;
       color: #969696;
   }
.second-comment i:hover{
       color: #333 !important;
   }
.second-comment .hint{
       float: left;
       margin: 17px 0 0 20px;
       font-size: 13px;
       color: #969696;
   }
.second-comment .cancel{
       float: right;
       font-size: 16px;
       margin: 18px 30px 0 0;
       color: #969696 !important;
   }
 .second-comment .cancel:hover{
       color: #2f2f2f !important;
   }
.second-comment .btn-send{
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
.second-comment .btn-send:hover{
       background: #3db922;
   }
 .second-comment .emoji-modal-warp .emoji-modal{
       position: absolute;
       top:50px;
       left: -48px;
       width: 402px;
       height: 208px;
       padding: 10px;
       background: #fff;
       border: 1px solid #d9d9d9;
       border-radius: 4px;
       box-shadow: 0 5px 25px rgba(0, 0, 0, 0.1);
       z-index:10000;
   }
</style>