<template>
  <div class="dropdown">
    <button class="btn btn-secondary dropdown-toggle" type="button" id="dropdownMenuButton1" @click.prevent="toggleOpen" data-bs-toggle="dropdown" aria-expanded="false">
      你好{{title}}
    </button>
    <ul class="dropdown-menu" aria-labelledby="dropdownMenuButton1" v-if="isOpen" style="display: block">
      <li><a class="dropdown-item" href="#">新建文章</a></li>
      <li><a class="dropdown-item" href="#">编辑资料</a></li>
    </ul>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue'

export default defineComponent({
  name: 'Dropdown',
  props: {
    title: {
      type: String,
      required: true
    }
  },
  setup () {
    const isOpen = ref(false)
    const toggleOpen = () => {
      isOpen.value = !isOpen.value
    }
    return {
      isOpen,
      toggleOpen
    }
  }
})
</script>
