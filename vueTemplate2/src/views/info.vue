<template>
  <div>
    hello info vue
    <button type="button" v-on:click="add()">打印</button>
  </div>
</template>

<script>
import store from '@/store'
export default {
  name: 'info',
  store,
  methods: {
    add () {
      console.log('console add methods')
      store.commit('add')
    }
  }
}
</script>
