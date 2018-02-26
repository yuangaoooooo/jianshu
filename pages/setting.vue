<template>
    <div>
        <my-header></my-header>
        <div class="main">
            <div class="aside">
                <ul>
                    <li :class="{isActive:this.$route.path=='/setting/jcsz'}">
                        <nuxt-link to="/setting/jcsz">
                            <i class="fa fa-file-text "></i>基础设置
                        </nuxt-link>
                    </li>
                    <li :class="{isActive:this.$route.path=='/setting/grzl'}">
                        <nuxt-link to="/setting/grzl">
                            <i class="fa fa-address-book "></i>个人资料
                        </nuxt-link>
                    </li>
                    <li :class="{isActive:this.$route.path=='/setting/wbrz'}">
                        <nuxt-link to="/setting/wbrz">
                            <i class="fa fa-hourglass  "></i>微博认证
                        </nuxt-link>
                    </li>
                    <li :class="{isActive:this.$route.path=='/setting/zssz'}">
                        <nuxt-link to="/setting/zssz">
                            <i class="fa fa-microchip "></i>赞赏设置
                        </nuxt-link>
                    </li>
                </ul>
            </div>
            <nuxt-child></nuxt-child>
        </div>
    </div>
</template>
<script>
    import myHeader from '../components/myHeader.vue'
    export default {
        name:'message',
        components:{
            myHeader
        },
        data () {
            return {
                
            }
        },
        methods:{
         
        },
        mounted () {
            
        }
    }
</script>
<style scoped>
@media (min-width:992px){
    .main {
        width: 960px;
    }
    .aside{
        width: 280px;
    }
    
}

@media (max-width:1080px){
    .main {
        width: 750px;
    }
    .aside{
        width: 220px;
    }
}   
.main{
    margin: 0 auto;
    padding-top: 30px;
}
.aside{
    float: left;
}
.aside ul a{
    height: auto;
    padding: 10px 25px;
    line-height: 30px;
    display: block;
}
.aside ul li{
    border-radius: 4px;
    font-size: 15px;
}

.aside ul li:hover{
    background-color: #f0f0f0;
}
.aside ul a i{
    color: white;
    margin-right: 20px;
    width: 35px;
    height: 35px;
    background-color: #a0a0a0;
    font-size: 20px;
    line-height: 35px;
    text-align: center;
    border-radius: 5px;
}
nuxt-child{
    float: right;
}
.isActive{
    background-color: #f0f0f0;
}
</style>