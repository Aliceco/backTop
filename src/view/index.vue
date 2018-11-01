<style>
  #indexContent {
    height: 100%;
    position: absolute;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    overflow: auto;
  }
  .index_content {
    text-align: center;
  }
  /*列表*/
  .index_list_content {
  }
</style>
<template>
  <div class="index_content" id="indexContent">
    <backTop :container="container"></backTop>
    <h1>{{ msg }}</h1>
    <div class="index_list_content">
      <div class="index_list_li_content" v-for="(item, index) in dataList" :key="index">
        <h4>{{item.name}}</h4>
      </div>
    </div>
  </div>
</template>

<script>
import backTop from '../components/backTop.vue'
export default {
  components: {
    backTop
  },
  data () {
    return {
      container: 'indexContent', // 返回顶部容器id
      msg: '返回顶部测试',
      dataList: ''
    }
  },
  mounted () {
  },
  created () {
    var temporary = []
    for (var i = 0; i <= 30; i++) {
      var src = {
        name: 'test' + i
      }
      temporary.push(src)
    }
    this.dataList = temporary
  }
}
</script>
