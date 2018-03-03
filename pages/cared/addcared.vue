<template>
    <div>
        <div class="con">
            <ul class="trigger-menu">
                    <li :class="{active:currentTab == 'alltuijian'}">
                        <a href="javascript:void(0)" @click="toggleTab('alltuijian')">
                            全部推荐
                        </a>
                    </li>
                    <li :class="{active:currentTab == 'tuijianuser'}">
                        <a href="javascript:void(0)" @click="toggleTab('tuijianuser')">
                            <i class="fa fa-user"></i>
                            推荐作者
                        </a>
                    </li>
                    <li :class="{active:currentTab == 'tuijianzuanti'}">
                        <a href="javascript:void(0)" @click="toggleTab('tuijianzuanti')">
                            <i class="fa fa-th-large"></i>
                            推荐专题
                        </a>
                    </li>
                </ul>
                <div id="list-container">
                    <!--动态组件-->
                    <component :is="currentTab" keep-alive></component>
                </div>
        </div>
    </div>
</template>
<script>
    import alltuijian from '@/components/cared/alltuijian'
    import tuijianuser from '@/components/cared/tuijianuser'
    import tuijianzuanti from '@/components/cared/tuijianzuanti'
export default {
    name:'addcared',
    components:{
        alltuijian,tuijianuser,tuijianzuanti
        },
        data () {
            return {
                currentTab:'alltuijian',
            }
        },
        methods: {
            toggleTab:function(tab){
                this.currentTab = tab;
            },
        }
}
</script>
<style scoped>
@media (min-width:992px){
    .con{
        margin-left: 260px;
    }
    
}

@media (max-width:1080px){
    .con{
        margin-left: 200px;
    }
}  
.con{
    padding-left: 20px;
}
</style>