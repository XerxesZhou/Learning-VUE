<template>
  <div>
    <div class="Weekend-title">周末去哪</div>
    <ul>
      <li class="Weekend-item border-bottom" v-for="item of list" :key="item.id">
        <div class="Weekend-item-img-wrapper">
          <img :src="item.imgUrl" alt class="item-img " />
        </div>
        <div class="Weekend-item-info">
          <p class="Weekend-item-title">{{item.title}}</p>
          <p class="Weekend-item-desc">{{item.desc}}</p>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "HomeWeekend",
  props: {
    list: Array
  }
};
</script>

<style lang="stylus" scoped>
@import '~@/assets/styles/mixins.styl';

.Weekend-title {
  line-height: 0.8rem;
  background: #eee;
  text-indent: 0.2rem;
}

.Weekend-item-img-wrapper {
  overflow: hidden;
  position: relative;
  height: 0;
  padding-bottom: 38%;

  img {
    width 100%
  }
}

.Weekend-item-info {
  flex: 1;
  padding: 0.1rem;
  min-width: 0;

  .Weekend-item-title {
    line-height: 0.54rem;
    font-size: 0.32rem;
    ellipsis();
  }

  .Weekend-item-desc {
    line-height: 0.44rem;
    color: #ccc;
    ellipsis();
  }
}
</style>