# backTop
使用vue实现返回顶部的插件
![](https://github.com/Aliceco/backTop/raw/master/static/img/2018-11-01_14-37-12.gif)

# 注意点
### 父组件的容器样式要全屏（可参考index.vue的css）<br />


# 引入组件
    #indexContent {
        height: 100%;
        position: absolute;
        top: 0;
        right: 0;
        bottom: 0;
        left: 0;
        overflow: auto;
      }
    <div class="index_content" id="indexContent">
      <backTop :container="container"></backTop>
      列表内容......
    </div>
    import backTop from '../components/backTop.vue'
    export default {
      components: {
        backTop
      },
      data () {
        return {
          container: 'indexContent' // 返回顶部容器id
        }
      },
      mounted () {
      },
      created () {
      }
    }

