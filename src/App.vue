<template>
  <div class="container">
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <!-- <HelloWorld msg="Welcome to Your Vue.js + TypeScript App"/> -->
    <ColumnList :list="list"/>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
// import HelloWorld from './components/HelloWorld.vue'
import ColumnList, { ColumnProps } from './components/ColumnList.vue'
import 'bootstrap/dist/css/bootstrap.min.css'
const testData: ColumnProps[] = [
  {
    id: 1,
    title: '数据展示需要记录当前节点及当前页',
    description: '数据展示需要记录当前节点及当前页, 否则用户刷新后将失去当前页面定位',
    avatar: 'https://gitlab.forensix.cn/uploads/-/system/user/avatar/146/avatar.png?width=400'
  },
  {
    id: 2,
    title: '数据展示需要记录当前节点及当前页',
    description: '数据展示需要记录当前节点及当前页, 否则用户刷新后将失去当前页面定位',
    avatar: 'https://gitlab.forensix.cn/uploads/-/system/user/avatar/146/avatar.png?width=400'
  },
  {
    id: 3,
    title: '数据展示需要记录当前节点及当前页',
    description: '数据展示需要记录当前节点及当前页, 否则用户刷新后将失去当前页面定位',
    avatar: 'https://gitlab.forensix.cn/uploads/-/system/user/avatar/146/avatar.png?width=400'
  },
  {
    id: 4,
    title: '数据展示需要记录当前节点及当前页',
    description: '数据展示需要记录当前节点及当前页, 否则用户刷新后将失去当前页面定位',
    avatar: 'https://gitlab.forensix.cn/uploads/-/system/user/avatar/146/avatar.png?width=400'
  },
  {
    id: 5,
    title: '数据展示需要记录当前节点及当前页',
    description: '数据展示需要记录当前节点及当前页, 否则用户刷新后将失去当前页面定位',
    avatar: 'https://gitlab.forensix.cn/uploads/-/system/user/avatar/146/avatar.png?width=400'
  },
  {
    id: 6,
    title: '数据展示需要记录当前节点及当前页',
    description: '数据展示需要记录当前节点及当前页, 否则用户刷新后将失去当前页面定位',
    avatar: 'https://gitlab.forensix.cn/uploads/-/system/user/avatar/146/avatar.png?width=400'
  },
  {
    id: 7,
    title: '数据展示需要记录当前节点及当前页',
    description: '数据展示需要记录当前节点及当前页, 否则用户刷新后将失去当前页面定位',
    avatar: 'https://gitlab.forensix.cn/uploads/-/system/user/avatar/146/avatar.png?width=400'
  }
]
export default defineComponent({
  name: 'App',
  components: {
    // HelloWorld,
    ColumnList
  },
  setup () {
    return {
      list: testData
    }
  }
})
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
