<template>
  <div>
    vue3 新特性
  </div>
  <div>计时器{{ counter }}</div>
  <van-button type="primary" @click="add">add</van-button>

  <div>ref使用对象:用户年龄{{ age }} 用户名字{{ name }}</div>
  <van-button @click="addAge" type="primary">修改年龄</van-button>
</template>

<script lang="ts">
import { reactive, ref, toRefs, watchEffect } from 'vue'
import { Button, Toast } from 'vant'

export default {
  components: {
    [Button.name]: Button
  },
  setup() {
    // 计时器
    const counter = ref(0)
    const add = () => {
      counter.value++
    }

    const user = reactive({ name: 12, age: 11 })
    const addAge = () => {
      user.age++
    }
    // 自动收集依赖 查看响应数据的变化
    // watchEffect 不需要手动传入依赖
    // watchEffect 会先执行一次用来自动收集依赖
    // watchEffect 无法获取到变化前的值， 只能获取变化后的值
    watchEffect(() => {
      Toast(user.age)
    })
    // watch(
    //   () => user.age,
    //   (curAge, preAge) => {
    //     console.log('新值:', curAge, '老值:', preAge)
    //   }
    // )

    const state = reactive({
      room: {
        id: 100,
        attrs: {
          size: '140平方米',
          type: '三室两厅'
        }
      }
    })

    return { counter, add, ...toRefs(user), addAge, ...toRefs(state) }
  }
}
</script>
<style lang="scss" scoped></style>
