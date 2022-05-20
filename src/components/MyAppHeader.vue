<template>
  <header>
    <div class="header_wrapper">
      <img src="../assets/img/logo-small.svg" alt="">
    </div>
  </header>
</template>

<script>
export default {
  name: 'MyAppHeader',
 
}
</script>

<style scoped lang="scss">
@import "../style/variables.scss";


.header_wrapper{
  height: 60px;
  display: flex;
  align-items: center;
  background-color: $brand-primary-color;

  img{
    height: 40px;
    width: 40px;
    margin: 1rem;
  }
}
</style>
