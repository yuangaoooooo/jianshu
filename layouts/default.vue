<template>
  <div id="default-template">
    <nuxt/>
  </div>
</template>
<script>
import Vue from 'vue'
import BootstrapVue from 'bootstrap-vue'
Vue.use(BootstrapVue)
// 时间过滤器
Vue.filter('formatDate',function(value){
  var d = new Date(value);
  var year = d.getFullYear();
  var month = d.getMonth() + 1;
  var day = d.getDate();
  var hour = d.getHours();
  var minutes = d.getMinutes();
  var seconds = d.getSeconds();
  function fillZero(num){
    return num >10 ? num : '0' + num;
  }
  return  fillZero(year)+ '.' + fillZero(month) + '.' + fillZero(day) + ' ' + fillZero(hour) + ':' + fillZero(minutes) + ':' + fillZero(seconds);
})
import 'bootstrap/dist/css/bootstrap.css'
import 'bootstrap-vue/dist/bootstrap-vue.css'

export default {

}
</script>
