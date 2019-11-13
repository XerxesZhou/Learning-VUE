<template>
  <div class="header">
    <div class="header-left">
        <span class='iconfont icon-back'>&#xe624;</span>
    </div>
    <div class="header-input">
        <span class='iconfont icon-search'>&#xe632;</span>
        输入城市/景点/游玩主题
    </div>
    <div class="header-right">
        城市
        <span class='iconfont icon-city'>&#xe64a;</span>
    </div>
  </div>
</template>
<script>
    export default {
      name: "HomeHeader"
    };
</script> 
<style lang="stylus" scoped>
    @import '~@/assets/styles/varibles.styl';
    .header
        display flex
        line-height .86rem
        background $bgColor
        color #fff
        .header-left
            width .64rem
            float left
            .icon-back 
                display block
                text-align center
                font-size  .4rem
        .header-input
            flex 1
            height .64rem
            line-height .64rem
            margin  .12rem .2rem
            background #fff
            border-radius .1rem
            color #ccc
            .icon-search
                margin-left .2rem
        .header-right
            width 1.24rem
            float right
            text-align center
            .icon-city
                margin-left -.05rem
                font-size  .24rem

</style>