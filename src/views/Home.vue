<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" />
    <HelloWorld msg="Wel11222333333come to Your Vue.js + TypeScript App" />
  </div>
  <van-button type="primary" block>块级元素</van-button>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import HelloWorld from '@/components/HelloWorld.vue' // @ is an alias to /src
import { Button } from 'vant'

export default defineComponent({
  name: 'Home',
  components: {
    HelloWorld,
    [Button.name]: Button
  }
})
</script>
