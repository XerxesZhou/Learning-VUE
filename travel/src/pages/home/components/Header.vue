<template>
  <div class="header">
    <div class="header-left">
      <span class="iconfont icon-back">&#xe624;</span>
    </div>
    <div class="header-input">
      <span class="iconfont icon-search">&#xe632;</span>
      输入城市/景点/游玩主题
    </div>
    <router-link to='/city'>
      <div class="header-right">
        {{this.city}}
        <span class="iconfont icon-city">&#xe64a;</span>
      </div>
    </router-link>
  </div>
</template>
<script>
import { mapState } from 'vuex'
export default {
  name: "HomeHeader",
  computed: {
    ...mapState(['city'])
  }
};
</script> 
<style lang="stylus" scoped>
@import '~@/assets/styles/varibles.styl';

.header {
  display: flex;
  line-height: $headerHeight;
  background: $bgColor;
  color: #fff;

  .header-left {
    width: 0.64rem;
    float: left;

    .icon-back {
      display: block;
      text-align: center;
      font-size: 0.4rem;
    }
  }

  .header-input {
    flex: 1;
    height: 0.64rem;
    line-height: 0.64rem;
    margin: 0.12rem 0.2rem;
    background: #fff;
    border-radius: 0.1rem;
    color: #ccc;

    .icon-search {
      margin-left: 0.2rem;
    }
  }

  .header-right {
    min-width: 1.04rem;
    padding 0 .1rem
    float: right;
    text-align: center;
    color: #fff;

    .icon-city {
      margin-left: -0.05rem;
      font-size: 0.24rem;
    }
  }
}
</style>