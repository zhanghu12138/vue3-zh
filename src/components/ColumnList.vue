<template>
  <div class="row">
    <div v-for="column in list" :key="column.id" class="col-4">
      <div class="card" style="margin-top: 30px">
        <div class="card-body">
          <img :src="column.avatar" class="rounded-circle border border-light w-25 my-3">
          <h5 class="card-title">{{column.title}}</h5>
          <p class="card-text text-left">{{column.description}}</p>
          <router-link :to="{name: 'column', params: { id:column.id }}">
            <a href="#" class="btn btn-outline-primary">Go somewhere</a>
          </router-link>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent, PropType } from 'vue'
export interface ColumnProps {
  id: number,
  title: string,
  avatar: string,
  description: string
}
export default defineComponent({
  name: 'ColumnList',
  props: {
    list: {
      type: Array as PropType<ColumnProps[]>,
      required: true
    }
  },
  setup (props) {
    console.log(props.list[0])
    return {}
  }
})
</script>
