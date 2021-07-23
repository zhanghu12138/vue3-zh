<template>
  <div>
    <pre>{{router}}</pre>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import { useRoute } from 'vue-router'

export default defineComponent({
  name: 'Column',
  setup () {
    const router = useRoute()
    return {
      router
    }
  }
})
</script>
