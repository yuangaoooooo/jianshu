<template>
    <div>
        <div class="main">
            <div class="content-jichu">
                <table>
                    <tr class="name">
                        <td class="nic">性别</td>
                        <td>
                            <input type="radio">&nbsp;男&#x3000;
                            <input type="radio">&nbsp;女&#x3000;
                            <input type="radio" checked>&nbsp;保密
                        </td>
                    </tr>
                    <tr class="name">
                        <td class="nic">个人简介</td>
                        <td>
                            <textarea name="" id="" cols="30" placeholder="填写你的个人简介"></textarea>
                        </td>
                    </tr>
                    <tr class="name">
                        <td class="nic">个人网站</td>
                        <td class="inp">
                            <input type="text" name="" id="" placeholder="http://你的网址">
                        </td>
                    </tr>
                    <tr class="name">
                        <td class="nic">微信二维码</td>
                        <td class="inp">
                            <div class="btn2">更换图片</div>
                            <span class="mini">上传后会在个人主页显示图标</span>
                        </td>
                    </tr>
                    <tr class="name">
                        <td class="nic">社交账号</td>
                        <td class="inp">
                            <p class="mini">你可以通过绑定的社交帐号登录简书。出于安全因素, 你最初用来创建账户的社交帐号不能移除。</p>
                            <p class="mini">如果帐号被占用，你可以在
                                <a href="javascript:;">简书帐号绑定解绑相关问题汇总</a>
                                中获得相关帮助。
                            </p>
                            <ul>
                                <li>
                                    <i class="fa fa-weibo weibo"></i>
                                    绑定微博
                                    <span class="fa fa-angle-right"></span>
                                </li>
                                <li>
                                    <i class="fa fa-weixin weixin"></i>
                                    绑定微信
                                    <span class="fa fa-angle-right"></span>
                                </li>
                                <li>
                                    <i class="fa fa-qq qq"></i>
                                    绑定qq
                                    <span class="fa fa-angle-right"></span>
                                </li>
                                <li>
                                    <i class="fa fa-snowflake-o douban"></i>
                                    绑定豆瓣
                                    <span class="fa fa-angle-right"></span>
                                </li>
                                <li>
                                    <i class="fa fa-google-plus google"></i>
                                    绑定谷歌
                                    <span class="fa fa-angle-right"></span>
                                </li>
                            </ul>
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
        name:'grzl',
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
    color: #42c02e;
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
    width: 50px;
    height: 30px;
    line-height: 15px;
    font-size: 14px;
    text-align: center;
    border: #42c02e 1px solid;
    color: #42c02e;
    border-radius: 30px;
    cursor: pointer;
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