<template>
    <div>
        <myHeader></myHeader>
        <div class="main">
            <h3>新建专题</h3>
            <table>
                <tbody>
                    <tr class="name">
                        <td class="nic">
                            <img class="avatar" src="../../assets/img/zhuanti.png" alt="">
                        </td>
                        <td>
                            <a href="javascript:;" class="change">
                                上传专题封面
                            </a>
                        </td>
                    </tr>
                    <tr class="name">
                        <td class="nic">名称</td>
                        <td class="inp">
                            <input class="real-input" type="text" placeholder="填写名称，不超过50个字">
                        </td>
                    </tr>
                    <tr class="name">
                        <td class="nic float-left">描述</td>
                        <td>
                            <textarea  placeholder="填写描述"></textarea>
                        </td>
                    </tr>
                    <tr class="name">
                        <td class="nic">其他管理员</td>
                        <td class="inp">
                            <input class="real-input" type="text" placeholder="输入用户名">
                        </td>
                    </tr>
                    <tr class="name">
                        <td class="nic">是否允许投稿 </td>
                        <td class="inp">
                            <input type="radio" name="yunxu" @click="allow" checked>&nbsp;允许&nbsp;&#x3000;&#x3000;
                            <input type="radio" name="yunxu" @click="noAllow">&nbsp;不允许
                        </td>
                    </tr>
                    <tr class="name" :class="{disabled}">
                        <td class="nic">投稿是否需要审核</td>
                        <td class="inp">
                            <input  :class="{noxuan:disabled}" type="radio" name="xuyao" checked>&nbsp;需要&nbsp;&#x3000;&#x3000;
                            <input  :class="{noxuan:disabled}" type="radio" name="xuyao">&nbsp;不需要
                        </td>
                    </tr>    
                </tbody>
            </table>
            <div class="anniu">
                创建专题
            </div>
        </div>
    </div>
</template>
<script>
    import myHeader from '../../components/myHeader.vue'
    export default {
        name:'new',
        components:{
            myHeader
        },
        data () {
            return {
                disabled:false,
            }
        },
        methods:{
            noAllow:function(){
                this.disabled = true;
            },
            allow:function(){
                this.disabled = false;
            }

        }
    }
</script>
<style scoped>
@media (min-width:992px){
    .main {
        width: 690px;
    }
}
@media (max-width:1080px){
    .main {
        width: 530px;
    }
}
@media (max-width:750px){
    .main {
        width: 100%;
        padding: 0 20px;
    }
    td{
        display: block;
    }
}
.main{
    margin-bottom: 60px;
    margin: 40px auto;
}
.main h3{
    margin: 10px 0 20px;   
    font-size: 21px;
    font-weight: 700;
    color: #333;
}
.main table{
    width: 100%;
}
.main table tr td{
    padding: 20px 0;
}
.float-left{
    float: left !important;
    margin: 0;
}
.main .avatar{
    width: 100px;
    height: 100px;
    border-radius: 10px;
}
.main .change{
    display: inline-block;
    vertical-align: middle;
    border: 1px solid #42c02e;
    width: 100px;
    height: 30px;
    border-radius: 30px;
    font-size: 14px;
    line-height: 30px;
    text-align: center;
    color: #42c02e !important;
}
.main .name .nic{
    width: 150px;
    font-size: 15px;
    color: #969696;
}
.main .name .real-input{
    width: 100%;
    height: 45px;
}
.main .name input{
    padding: 5px 10px;
    font-size: 15px;
    border: 1px solid #c8c8c8;
    border-radius: 4px;
    background-color:#f8f8f8;
}
.main .name .inp{
    font-size: 15px;
}
.main .disabled{
    color: #ddd !important;
    opacity: 0.3;   
}
.noxuan{
    cursor: not-allowed;
}
.main .anniu{
    width: 100px;
    height: 40px;
    border-radius: 30px;
    margin: 20px 0;
    background-color: #42c02e;
    color: white !important;
    line-height: 40px;
    text-align: center;
    cursor: pointer;
}
textarea{
    width: 100%;
    height: 100px;
    resize: none;
    padding: 5px 10px;
    font-size: 15px;
    border: 1px solid #c8c8c8;
    border-radius: 4px;
    background-color:#f8f8f8;
}
</style>