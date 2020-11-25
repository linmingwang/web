<template>
  <div id="nav">
    {{id}}--{{name}}
    <button @click="change">click</button>
  </div>
  <router-view/>
</template>

<script>
import { reactive, toRefs } from 'vue'
export default {
  setup (props, context) {
    // 创建响应式数据对象 reactive({ id: 1 }) 接收一个普通对象，返回一个响应对象
    const state = reactive({
      id: 1,
      name: 'lmw'
    })
    // 方法定义
    const change = () => {
      state.id += 1
    }
    // setup函数将响应式数据对象return出去供template使用
    return {
      ...toRefs(state), // 解构赋值
      change
    }
  }
}
</script>

<style lang="scss">

</style>
