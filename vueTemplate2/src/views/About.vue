<template>
  <div class="about">
    <h1>This is an about page</h1>
    <h2>{{msg}}</h2>
  </div>
</template>

<script>
import store from '@/store'
export default {
  name: 'About',
  store,
  data () {
    return {
      msg: store.state.count
    }
  }
}
</script>
