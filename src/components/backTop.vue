<style>
  #backTop_content {
    z-index: 99999999;
    position: fixed;
    right: 12px;
    bottom: 12px;
  }
  .backTop_button_content {
    width: 60px;
    height: 60px;
    display: flex;
    justify-content: center;
    align-items: center;
    border-radius: 100%;
    /*border: 1px solid #ccc;*/
    background-color: #2196f3;
  }
  .backTop_button_content img {
    width: 30px;
    height: 30px;
  }
  /* 动画 */
  .backTop_show {
    animation: backTopShow ease 300ms;
  }

  .backTop_hide {
    animation: backTopHide ease 500ms;
  }

  @keyframes backTopShow {
    0% {
      opacity: 0;
      transform: translate3d(0, 0, 0) scale(0);
    }
    100% {
      opacity: 1;
      transform: translate3d(0, 0, 0) scale(1);
    }
  }

  @keyframes backTopHide {
    0% {
      opacity: 1;
      transform: translate3d(0, 200, 0) scale(1);
    }
    100% {
      opacity: 0;
      transform: translate3d(0, 0, 0) scale(0);
    }
  }
</style>
<template>
  <div id="backTop_content" v-show="isTopButton" :class="isTopButton? 'backTop_show' : 'backTop_hide'">
    <div class="backTop_button_content" @click="backTopButton">
      <img src="/static/img/arrows.png" alt="">
    </div>
  </div>
</template>

<script>
export default {
  name: 'backTop',
  props: {
    // 容器的id
    container: {
      type: String,
      default: ''
    }
  },
  data () {
    return {
      isTopButton: false // 按钮(true显示/false不显)
    }
  },
  mounted () {
    document.getElementById(this.container).addEventListener('scroll', this.handleScroll)
  },
  created () {
  },
  methods: {
    // 获取滚动条高度
    handleScroll () {
      var scrollTop = document.getElementById(this.container).scrollTop
      console.log(scrollTop)
      if (scrollTop > 100) {
        this.isTopButton = true // 显示
      } else {
        this.isTopButton = false // 隐藏
      }
    },
    // 返回顶部
    backTopButton () {
      document.getElementById(this.container).scrollTop = 0
    }
  }
}
</script>
