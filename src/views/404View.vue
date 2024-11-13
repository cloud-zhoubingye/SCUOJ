<template>
  <div class="clearfix container" style="height: 300px">
    <div class="_center">
      <div class="tip" style="display: inline-block">
        <div class="notfound">404</div>
        <span>The page was eaten by a naughty cat</span>
      </div>
      <div style="display: inline-block; float: right; margin: 30px 0 0 10px">
        <img :src="Img404" alt="TT with his magic cat" width="170">
      </div>
    </div>
  </div>
</template>

<script>
import Img404 from '@/assets/404.png';

export default {
  computed: {
    Img404: () => Img404
  }
}
</script>

<style lang="less" scoped>
  ._center {
    position: absolute;
    left: 50%;
    transform: translate(-50%, 0);
  }
  .tip {
    .notfound {
      text-align: center;
      padding-top: -20px;
      font-size: 10em;
    }
    span {
      font-size: 20px;
    }
  }
</style>
