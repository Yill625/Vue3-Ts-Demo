<template>
  <div class="wrapper">
    <div class="content">
      <img alt="Vue logo" src="../assets/logo.png" />
      <HelloWorld msg="Wel11222333333come to Your Vue.js + TypeScript App" />
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import HelloWorld from '@/components/HelloWorld.vue' // @ is an alias to /src
import { Button } from 'vant'
import BScroll from '@better-scroll/core'

export default defineComponent({
  name: 'Scroll',
  components: {
    HelloWorld,
    [Button.name]: Button
  },
  mounted() {
    this.$nextTick(() => {
      new BScroll('.wrapper')
    })
  }
})
</script>

<style lang="css" scoped>
.wrapper {
  height: 600px;
  overflow: hidden;
}
.content {
}
</style>
