<template>
  <div id="app">

    <Header></Header>
    <router-view/>
  </div>
</template>

<style>


</style>

<script>
import Header from "@/components/Header.vue";

export default {
  name: 'APP',
  components: {

    Header

  }
}
</script>
