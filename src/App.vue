<template>
  <div id="app">
    <MyHeade title="购物车案例" background="tomato" color="#fff"></MyHeade>
    <MyGoods
      v-for="item in goodlist"
      :key="item.goods_id"
      :goods="item"
    ></MyGoods>
    <MyFooter :goodlist="goodlist"></MyFooter>
  </div>
</template>

<script>
import MyHeade from './components/MyHeade.vue'
import MyGoods from './components/MyGoods.vue'
import MyFooter from './components/MyFooter.vue'
import 'bootstrap/dist/css/bootstrap.min.css'
import axios from 'axios'
export default {
  components: { MyHeade, MyGoods, MyFooter },
  data () {
    return {
      goodlist: []
    }
  },
  created () {
    this.getGoods()
    // console.log(this.res.data.list)
  },
  methods: {
    async getGoods () {
      const res = await axios({
        url: '/api/cart'
      })
      this.goodlist = res.data.list
      // console.log(res.data.list)
    }
  }
}
</script>

<style scoped>
#app {
  padding: 50px 0;
}
</style>
