<template>
  <div class="index">
    <h2 class="title">封装组件better-scroll滚动<br/>  以及上拉下拉刷新</h2>
    <h2 class="text">列表</h2>
    <scroll class="box" :data="list" :pulldown="pulldown" @pulldown="loadData">
        <ul>
          <li v-for="(item,index) in list" :key="index">
            <img :src="item.img" alt="">
          </li>
        </ul>
    </scroll>
  </div>
</template>

<script>
import Scroll from '@/base/scroll/scroll'
export default {
  name: 'index',
  data () {
    return {
      list:[{
          id:1,
          img:'http://img3.imgtn.bdimg.com/it/u=2957286837,1770710086&fm=26&gp=0.jpg'
        },{
          id:2,
          img:'http://img2.imgtn.bdimg.com/it/u=1206685234,500217256&fm=26&gp=0.jpg'
        },{
          id:3,
          img:'http://img4.imgtn.bdimg.com/it/u=1843568763,107432329&fm=26&gp=0.jpg'
        }
      ]
    }
  },
  components: {
    Scroll
  },
  methods: {
    loadData () {
      // 调用api获取数据
    }
  }
}
</script>

<style lang="less" scoped>
.index {
  position: fixed;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  >.title {
    text-align: center;
    font-size: 18px;
  }
  .text {
    font-size: 16px;
    line-height: 30px;
    padding-left: 10px;
  }
  ul {
    width: 100%;
    overflow: hidden;
    li {
      width: 100%;
      padding: 10px;
      box-sizing: border-box;
      >img {
        width: 100%;
        height: 500px;
      }
    }
  }
}
</style>

