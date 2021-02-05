<template>
  <div class="home">
    <input type="number" pattern="\d*" />
    <img alt="Vue logo" src="../assets/logo.png" />
    <HelloWorld msg="Wel11222333333come to Your Vue.js + TypeScript App" />
  </div>
  <van-button type="primary" block>块级元素{{ a }}</van-button>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import HelloWorld from '@/components/HelloWorld.vue' // @ is an alias to /src
import { Button } from 'vant'

export default defineComponent({
  name: 'Home',
  data() {
    const tset = { a: 0 }
    return {
      a: tset?.a ?? 2
    }
  },
  components: {
    HelloWorld,
    [Button.name]: Button
  }
})
</script>
