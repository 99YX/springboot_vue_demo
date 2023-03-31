<template>
  <div id="app">
   <!--  头部  -->
    <Header></Header>
    <!--  主体  -->
    <div style="display: flex">
     <!--  侧边栏    -->
      <Aside></Aside>
      <router-view></router-view>
    </div>


  </div>
</template>

<style>


</style>

<script>
import Header from "@/components/Header.vue";
import Aside from "@/components/Aside.vue";

export default {
  name: 'APP',
  components: {
    Aside,

    Header

  }
}
</script>
