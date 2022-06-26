<template>
  <div id="app">
    <MyHeade title="购物车案例" background="tomato" color="#fff"></MyHeade>
    <MyGoods></MyGoods>
    <MyFooter></MyFooter>
  </div>
</template>

<script>
import MyHeade from './components/MyHeade.vue'
import MyGoods from './components/MyGoods.vue'
import MyFooter from './components/MyFooter.vue'
import 'bootstrap/dist/css/bootstrap.min.css'
export default { components: { MyHeade, MyGoods, MyFooter } }
</script>

<style scoped>
#app {
  padding: 50px 0;
}
</style>
