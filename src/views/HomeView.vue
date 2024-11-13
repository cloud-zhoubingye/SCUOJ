<template>
  <div class="container">
    <!-- 轮播图 -->
    <Carousel
        v-model="carouselSettings.value"
        :autoplay="carouselSettings.autoplay"
        :autoplay-speed="carouselSettings.autoplaySpeed"
        :dots="carouselSettings.dots"
        :radius-dot="carouselSettings.radiusDot"
        :trigger="carouselSettings.trigger"
        :arrow="carouselSettings.arrow">
        <CarouselItem v-for="img in carouselImgs" :key="img">
          <div class="demo-carousel"><img :src="img" alt=""></div>
        </CarouselItem>
    </Carousel>
    <Row class="main">
      <Col span="16" class="main-lf">
        <Card title="Announcements" icon="ios-alert-outline" dis-hover :padding="10">
          <div style="margin: 0 10px">
            <Row class="announce-subtitle">
              <Col span="18">Title</Col>
              <Col span="6">Time</Col>
            </Row>
            <Row class="announce-item" v-for="item in announcements" :key="item.url">
              <Col span="18">{{ item.title }}</Col>
              <Col span="6">{{ item.time }}</Col>
            </Row>
          </div>
        </Card>
      </Col>
      <Col span="8" class="main-ri">
      <Card dis-hover title="Search" icon="ios-search">
        <template>
          <div class="global-search">
            <Input style="width: 100%; display: block;" type="text" autocomplete="off" placeholder="ID" />
          </div>
        </template>
      </Card>
      </Col>
    </Row>
  </div>
</template>

<script>

export default {
  data: function() {
    return {
      carouselSettings: {
        value: 0,
        autoplay: true,
        autoplaySpeed: 2000,
        dots: 'inside',
        radiusDot: false,
        trigger: 'click',
        arrow: 'hover'
      },
      carouselImgs: [
        // test imgs
        'https://www.scu.edu.cn/__local/A/9A/84/2C2CBE3111400A05AAFFD7F2745_05D5882E_11C7C9.jpg'
      ],
      announcements: [
        { title: 'SCU ACM OJ 将举办第一场比赛！', time: '2024-11-26', url: '1' },
        { title: 'SCU ACM OJ 已经成功上线啦！', time: '2020-11-01', url: '2' }
      ]
    }
  }
};
</script>

<style lang="less" scoped>
.demo-carousel {
  width: 100%;
  min-height: 300px;
  img {
    width: auto;
    height: auto;
    max-width: 100%;
    max-height: 100%;
  }
}

.main {
  .main-lf {
    padding: 24px 12px 0 0;
  }
  .main-ri {
    padding: 24px 0 0 12px;
  }
}

.announce-subtitle {
  height: 30px;
  font-weight: bold;
  display: -webkit-box;
  -webkit-box-align: center;
}
.announce-item {
  height: 40px;
  color: #2D7ABA;
  border-top: 1px solid #d4d4d5;
  display: -webkit-box;
  -webkit-box-align: center;
  :hover {
    cursor: pointer;
  }
}

.global-search {
  // margin-top: 10px;
  height: 30px;
  /deep/ .ivu-input {
    border-radius: 10px;
  }
}

</style>
