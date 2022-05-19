<template>
  <div id="app">
    <MyAppHeader />
    <MyAppMain />
  </div>
</template>

<script>
import MyAppHeader from './components/MyAppHeader.vue'
import MyAppMain from './components/MyAppMain.vue'

export default {
  name: 'App',
  components: {
    MyAppHeader,
    MyAppMain 

  }
}
</script>

<style lang="scss">
@import "./style/common.scss";



</style>
