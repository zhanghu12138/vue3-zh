<template>
  <div class="dropdown" ref="dropdownRef">
    <button class="btn btn-secondary dropdown-toggle" type="button" id="dropdownMenuButton1" @click.prevent="toggleOpen" data-bs-toggle="dropdown" aria-expanded="false">
      你好{{title}}
    </button>
    <ul class="dropdown-menu" aria-labelledby="dropdownMenuButton1" v-if="isOpen" style="display: block">
      <slot></slot>
    </ul>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref, onMounted, onUnmounted } from 'vue'

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
    const dropdownRef = ref<HTMLElement | null>(null)
    const toggleOpen = () => {
      isOpen.value = !isOpen.value
    }
    const handle = (e: MouseEvent) => {
      if (dropdownRef.value) {
        if (!dropdownRef.value.contains(e.target as HTMLElement) && isOpen.value) {
          console.log(isOpen)
          isOpen.value = false
        }
        console.log(dropdownRef)
      }
    }
    onMounted(() => {
      console.log(dropdownRef)
      document.addEventListener('click', handle)
    })
    onUnmounted(() => {
      document.removeEventListener('click', handle)
    })
    return {
      isOpen,
      toggleOpen,
      dropdownRef
    }
  }
})
</script>
