<template>
  <div class="container">
    <global-header :user="userInfo"></global-header>
    <router-view></router-view>
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <!-- <HelloWorld msg="Welcome to Your Vue.js + TypeScript App"/> -->
    <ColumnList :list="list"/>
    <login-form></login-form>
  </div>
</template>

<script lang="ts">
import { defineComponent, reactive } from 'vue'
// import HelloWorld from './components/HelloWorld.vue'
import ColumnList, { ColumnProps } from './components/ColumnList.vue'
import GlobalHeader, { UserProps } from './components/GlobalHeader.vue'
import loginForm from '@/views/Form.vue'
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
const userInfo: UserProps = {
  isLogion: true,
  name: '莉莉'
}

export default defineComponent({
  name: 'App',
  components: {
    // HelloWorld,
    ColumnList,
    GlobalHeader,
    loginForm
  },
  setup () {
    const emailRef = reactive({
      val: '',
      error: false,
      message: ''
    })
    return {
      list: testData,
      userInfo: userInfo,
      emailRef
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
  /* margin-top: 60px; */
}
</style>
