<template>
  <div class="page">
    <h2>{{msg}}</h2><hr>
    <h3>{{$store.state.count}}-{{count}}</h3>
    <!-- 获取state.count 通过三种方式来更简洁的获取count-->
    <p>
      <button @click="add(6)">+</button>
      <button @click="reduce">-</button>
    </p>
    <p>
      <button @click="addAction">+</button>
      <button @click="reduceAction">-</button>
    </p>
  </div>
</template>

<script type="text/ecmascript-6">
  import store from '@/vuex/store'
  import {mapState, mapMutations, mapGetters, mapActions} from 'vuex'
  export default {
    data() {
      return {
        msg: 'hello vuex'
      }
    },
    store,
    components: {

    },
    computed: {
      ...mapState(['count']),
      // count() {
      //   return this.$store.getters.count
      // }
      ...mapGetters(['count'])
    },
    methods: {
      ...mapMutations(['add', 'reduce']),
      ...mapActions(['addAction', 'reduceAction'])
    }
  }
</script>

<style scoped lang="stylus" rel="stylesheet/stylus">

 
</style>
