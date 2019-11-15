<template>
  <div>
    <div class="search">
      <input v-model="keyword" class="search-input" type="text" placeholder="输入城市名或拼音" />
    </div>
    <div class="search-content" ref="search" v-show="keyword">
      <ul>
        <li class="search-item border-bottom" 
            v-for="item of list" 
            :key="item.id"
            @click="handleCityClick(item.name)">{{item.name}}</li>
        <li class="search-item border-bottom" v-show="hasNoData">没有找到匹配数据</li>
      </ul>
    </div>
  </div>
</template> 

<script>
import Bscroll from 'better-scroll'
import { mapState , mapActions} from 'vuex'
export default {
  name: "CitySearch",
  props: {
    city: Object
  },
  data() {
    return {
      keyword: "",
      list: [],
      timer: null
    };
  },
  methods: {
    handleCityClick (city) {
      //this.$store.dispatch('changeCity',city);
      this.changeCity(city)//此处不用changeCity已经调用
      this.$router.push('/')
    },
    ...mapActions(['changeCity'])
  },
  computed: {
    hasNoData () {
      if (this.keyword){
        return !this.list.length
      }
    }
  },
  watch: {
    keyword() {
      if (this.timer) {
        clearTimeout(this.timer);
      }
      if(!this.keyword) {
        return this.list = []
      }
      this.timer = setTimeout(() => {
        const result = [];
        for (let i in this.city) {
          this.city[i].forEach(value => {
            if (
              value.spell.indexOf(this.keyword) >= 0 ||
              value.name.indexOf(this.keyword) >= 0
            ) {
              result.push(value);
            }
          });
        }
        this.list = result;
      }, 100);
    }
  },
  mounted () {
      this.scroll = new Bscroll(this.$refs.search)
  }
};
</script>

<style lang="stylus" scoped>
@import '~@/assets/styles/varibles.styl';

.search {
  height: 0.72rem;
  padding: 0 0.1rem;
  background: $bgColor;

  .search-input {
    box-sizing: border-box;
    width: 100%;
    height: 0.62rem;
    padding: 0 0.1rem;
    line-height: 0.62rem;
    text-align: center;
    border-radius: 0.06rem;
    color: #666;
  }
}

.search-content {
  overflow: hidden;
  position: absolute;
  z-index: 1;
  top: 1.58rem;
  left: 0;
  right: 0;
  bottom: 0;
  background: #fcfcfc;
}

.search-item {
  line-height: 0.62rem;
  padding-left: 0.2rem;
  color: #666;
  background: #fff;
}
</style>