<template>
    <div>
        <my-header></my-header>
        <div class="main">

        </div>
    </div>
</template>
<script>
    import myHeader from '../../components/myHeader.vue'
    export default {
        name:'jianxin',
        components:{
            myHeader
        },
        data () {
            return {
                
            }
        },

    }
</script>
<style scoped>
@media (min-width:992px){
    .main {
        width: 960px;
}
}
@media (max-width:1080px){
    .main {
        width: 750px;
    }
}
</style>