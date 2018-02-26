<template>
    <div>
        <div class="main">
            <div class="content-jichu">
                <div class="user">
                    <nuxt-link to="/" class="avatar">
                        <img src="../../assets/img/default-avatar.jpg" alt="">
                    </nuxt-link>
                    <nuxt-link to="/" class="change">
                        更换头像
                    </nuxt-link>
                    
                </div>
                <table>
                    <tr class="name">
                        <td class="nic">昵称</td>
                        <td><input type="text" placeholder="grooooooter"></td>
                    </tr>
                    <tr class="name">
                        <td class="nic">电子邮件</td>
                        <td>
                            <input type="text" placeholder="请输入你常用的邮箱">&#x3000;
                            <div class="btn">
                                发送
                            </div>
                        </td>
                    </tr>
                    <tr class="name" @mouseover="isshow=true" @mouseleave="isshow=false">
                        <td class="nic">手机</td>
                        <td class="inp">182****5789 &nbsp;
                            <span class="fa fa-check"></span>&nbsp;
                            <span>已验证</span>&nbsp;
                            <span class="nobang" v-if="isshow">解除绑定</span>
                        </td>
                    </tr>
                    <tr class="name">
                        <td class="nic">常用编辑器</td>
                        <td class="inp">
                            <input type="radio" checked>&nbsp;富文本 &#x3000;&#x3000;&#x3000;
                            <input type="radio">&nbsp;MarkDown
                        </td>
                    </tr>
                    <tr class="name">
                        <td class="nic">语言设置</td>
                        <td class="inp">
                            <input type="radio" checked>&nbsp;中文简体&nbsp;&#x3000;&#x3000;
                            <input type="radio">&nbsp;中文繁体
                        </td>
                    </tr>
                    <tr class="name">
                        <td class="nic">接收谁的简信</td>
                        <td class="inp">
                            <input type="radio" checked>&nbsp;所有人 &#x3000;&#x3000;&#x3000;
                            <input type="radio">&nbsp;我关注的人、我发过简信的人
                        </td>
                    </tr>
                    <tr class="name">
                        <td class="nic">提醒邮件通知</td>
                        <td class="inp">
                            <input type="radio" checked>&nbsp;所有动态&nbsp;&#x3000;&#x3000;
                            <input type="radio">&nbsp;每天汇总未读&#x3000;&#x3000;&#x3000;
                            <input type="radio">&nbsp;不接收
                        </td>
                    </tr>
                    <div class="anniu">
                        保存
                    </div>
                </table>
            </div>
                
        </div>
    </div>
</template>
<script>

    export default {
        name:'jcsz',
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
    .main{
        margin-left: 280px;
    }
    
}

@media (max-width:1080px){
    .main{
        margin-left: 220px;
    }
}  
.main{
    padding-top: 10px;
}

.main .content-jichu{
    padding-left: 10px;
}

.main .content-jichu .user .avatar{
    width: 100px;
    height: 100px;
    display: inline-block;
    vertical-align: middle;
    margin-right: 20px;
}
.main .content-jichu .user .change{
    display: inline-block;
    vertical-align: middle;
    border: 1px solid #42c02e;
    width: 80px;
    height: 30px;
    border-radius: 30px;
    font-size: 14px;
    line-height: 30px;
    text-align: center;
    color: #42c02e !important;
}
.main .content-jichu table{
    width: 100%;
}
.main .content-jichu table tr td{
    margin-top: 20px;
    border-bottom: 1px solid #eaeaea;
    padding: 20px 0;
}
.main .content-jichu .name .nic{
    width: 125px;
    font-size: 15px;
    color: #969696;
}
.main .content-jichu .name input{
    padding: 5px 10px;
    font-size: 15px;
    border: 1px solid #c8c8c8;
    border-radius: 4px;
    background-color:#f8f8f8;
}
.main .content-jichu .name .inp{
    font-size: 15px;
}
.main .content-jichu .name .inp span{
    font-size: 14px;
    color: #969696;
}
.btn{
    width: 54px;
    height: 29px;
    line-height: 15px;
    font-size: 14px;
    text-align: center;
    border: #42c02e 1px solid;
    color: #42c02e;
    border-radius: 40px;
    cursor: pointer;
    padding: 1px 12px;
}
.btn:hover{
    background-color: #f5fcf3;
}
.nobang:hover{
    color: black !important;
    cursor: pointer;
}
.main .content-jichu .anniu{
    width: 100px;
    height: 30px;
    border-radius: 30px;
    margin: 20px 0;
    background-color: #42c02e;
    color: white !important;
    line-height: 30px;
    text-align: center;
}
.btn2{
    width: 80px;
    height: 30px;
    line-height: 30px;
    font-size: 14px;
    text-align: center;
    border: #42c02e 1px solid;
    color: #42c02e;
    border-radius: 30px;
    cursor: pointer;
    display: inline-block;
    margin-right: 30px;
}
.btn2:hover{
    background-color: #f5fcf3;
}
.mini{
    font-size: 12px !important;
}
.name ul li{
    line-height: 50px;
    font-size: 14px;
    border-bottom: 1px solid #eaeaea;
}
.name ul li span{
    color: black !important;
}
textarea{
    padding: 5px 10px;
    font-size: 15px;
    border: 1px solid #c8c8c8;
    border-radius: 4px;
    background-color:#f8f8f8;
}
</style>