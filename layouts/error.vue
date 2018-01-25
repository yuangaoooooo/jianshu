<template>
  <section class="">
    <header>
      <img src="../assets/img/logo2.png" alt="">
    </header>
    <main>
      <img src="../assets/img/404.png" alt="">
      <p>
        {{ error.message }} <br>
        <span>可能是因为您的链接地址有误、该文章已经被作者删除或转为私密状态。</span>
        
      </p>
      <nuxt-link class="btn btn-success" to="/" v-if="error.statusCode === 404">
        返回【简书】首页
      </nuxt-link>
    </main>
    <!-- <h1 class="title">
      {{ error.statusCode }}
    </h1>
    <h2 class="info">
      {{ error.message }}
    </h2>
    <nuxt-link class="button" to="/" v-if="error.statusCode === 404">
      Homepage
    </nuxt-link> -->
  </section>
</template>
<script>
export default {
  props: ['error']
}
</script>

<style scoped>
header{
  width: 100%;
  height: 80px;
  position: relative;
}
header img{
  width: 300px;
  height: 40px;
  position: absolute;
  left: 40px;
  top: 40px;
}
main{
  width: 100%;
  text-align: center;
  padding-top: 20px;
}
main img{
  width: 220px;
  height: 200px;
  margin: 0 auto;
}
main p{
  margin: 30px 0;
  font-size: 20px;
  font-weight: 700;
}
main p span{
  font-weight: 200;
  font-size: 18px;
}
main a{
  border-radius: 20px;
  color: white !important;
}
/* .title
{
  margin-top: 15px;
  font-size: 5em;
}
.info
{
  font-weight: 300;
  color: #9aabb1;
  margin: 0;
}
.button
{
  margin-top: 50px;
} */

@media (max-width:768px){
    header img{
        display: none;
    }
}
</style>
