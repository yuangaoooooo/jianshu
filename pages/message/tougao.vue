<template>
    <div>
        <div class="con">
            <div class="top">全部投稿请求</div>
        </div>
    </div>
</template>
<script>
    export default {
        name:'tougao',
        components:{
            
        },
        data () {
            return {
                
            }
        },

    }
</script>
<style scoped>
@media (min-width:992px){
    .con{
        margin-left: 280px;
    }
    
}

@media (max-width:1080px){
    .con{
        margin-left: 220px;
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

</style>