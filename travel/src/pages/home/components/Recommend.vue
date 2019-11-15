<template>
  <div>
    <div class="recommend-title">热销推荐</div>
    <ul>
      <li class="recommend-item border-bottom" v-for="item of list" :key="item.id">
        <div class="recommend-item-img-wrapper">
          <img
            :src="item.imgUrl"
            alt
            class="item-img"
          />
        </div>
        <div class="recommend-item-info">
          <p class="recommend-item-title">{{item.title}}</p>
          <p class="recommend-item-desc">{{item.desc}}</p>
          <button class="recommend-item-button">查看详情</button>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "HomeRecommend",
  props: {
    list: Array
  }
};
</script>

<style lang="stylus" scoped>
@import '~@/assets/styles/mixins.styl';

.recommend-title {
  margin-top: 0.2rem;
  line-height: 0.8rem;
  background: #eee;
  text-indent: 0.2rem;
}

.recommend-item {
  overflow: hidden;
  display: flex;
  height: 1.9rem;
  padding .1rem

  .recommend-item-img-wrapper {
    overflow: hidden;
    position: relative;
    height: 0;
    width: 42%;
    padding-bottom: 25.5%;

    img {
      position: absolute;
      left: 0;
      top: 0;
      right: 0;
      bottom: 0;
      width 92%
      height 1.8rem
    }
  }

  .recommend-item-info {
    flex: 1;
    padding: 0.1rem;
    min-width 0

    .recommend-item-title {
      line-height: 0.54rem;
      font-size: 0.32rem;
      ellipsis();
    }

    .recommend-item-desc {
      line-height: 0.44rem;
      color: #ccc;
      ellipsis();
    }

    .recommend-item-button {
      margin-top: 0.16rem;
      background: #ff9300;
      padding: 0 0.1rem;
      border-radius: 0.06rem;
      color: #fff;
      line-height .44rem
    }
  }
}
</style>