<template>
    <div>
        <div class="main">
            <table>
                <tbody class="account">
                    <tr>
                        <td class="setting-title top-line">打包下载文章</td> 
                        <td class="top-line"><a href="javascript:;" class="btn btn-ok top-btn">下载所有文章</a></td>
                    </tr>
                </tbody>
            </table>
            <div class="delete-account-content">
                <a v-show="btnShow" @click="btnShow=false;formShow=true;" href="javascript:;" class="show-button">删除帐号<i class="fa fa-chevron-down"></i></a>
                <div class="content" v-show="formShow">
                    <h4>永久删除帐号</h4> 
                    <ul>
                        <li>如果你不小心创建出了多余的帐号，或在绑定帐号的时候提示帐号被占用，你可以在
                            <a class="lan" href="javascript:;">简书帐号绑定解绑相关问题汇总</a>中获得相关帮助。
                        </li> 
                        <li>如果你对简书上的某些内容、功能或社区规则不满意，你可以在
                            <a class="lan" href="javascript:;">帮助与反馈页</a>向我们提出。
                        </li> 
                        <li>删除帐号前，请确保已经没有任何公开或私密文章，且钱包中全部余额已清零。

                        </li> 
                        <li>删除帐号是不可逆的操作，删除后将无法恢复。</li>
                    </ul> 
                    <a @click="btnShow=true;formShow=false;" class="btn btn-ok">保留我的帐号</a> 
                    <a class="btn btn-delete">删除帐号</a>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
    export default {
        name:'zhgl',
        data () {
            return {
                btnShow:true,
                formShow:false,
            }
        },
        methods:{

        }
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
    padding-left: 20px;
}
.setting-title {
    font-size: 15px;
    color: #969696;
}
.delete-account-content{
    margin-top: 20px;
    padding-top: 20px;
    border-top: 1px solid #f0f0f0;
}
.delete-account-content .show-button {
    font-size: 15px;
    color: #969696 !important;
}
.delete-account-content .content h4{
    font-family: inherit;
    font-weight: 500;
    line-height: 1.1;
    color: inherit;
    font-size: 18px;
    margin-top: 10px;
}
.delete-account-content .content ul{
    list-style: circle;
}
.delete-account-content .content ul li{
    margin-bottom: 15px;
    line-height: 20px;
    font-size: 14px;
}
.top-btn{
    margin-left: 20px;
}
.btn-ok{
    padding: 4px 12px;
    font-size: 14px;
    font-weight: 400;
    line-height: normal;
    border-radius: 40px;
    border: 1px solid rgba(59,194,29,.7);
    color: #42c02e!important;
    cursor: pointer;
}
.btn-delete{
    padding: 4px 12px;
    font-size: 14px;
    font-weight: 400;
    line-height: normal;
    border-radius: 40px;
    border: 1px solid rgba(236,97,73,.7);
    color: #ea6f5a!important;
    margin-left: 20px;
    cursor: pointer;
}
.lan{
    color: #3194d0 !important;
}
</style>