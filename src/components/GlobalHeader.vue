<template>
  <nav class="navbar navbar-light">
    <div class="container">
      <a class="navbar-brand" href="#">
        <img src="@/assets/bootstrap-logo.svg" width="30" height="24">
      </a>
      <div v-if="!user.isLogion">
        <button class="btn btn-outline-primary mx-2" type="submit">登录</button>
        <button class="btn btn-outline-primary mx-2" type="submit">注册</button>
      </div>
      <div v-else>
        <dropdown :title="user.name"></dropdown>
      </div>
    </div>
  </nav>
</template>

<script lang="ts">
import { defineComponent, PropType } from 'vue'
import Dropdown from './Dropdown.vue'
export interface UserProps {
  isLogion: boolean,
  name?: string,
  id?: number
}
export default defineComponent({
  name: 'GlobalHeader',
  props: {
    user: {
      type: Object as PropType<UserProps>,
      required: true
    }
  },
  components: {
    Dropdown
  }
})
</script>
