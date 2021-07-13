<template>
  <li class="dropdown-item">
    <slot></slot>
  </li>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'DropdownItem',
  setup () {
    return {}
  }
})
</script>
