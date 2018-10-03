<!--用户基本信息页面-->
<style scoped lang="scss">
.p-user-data {
  margin: 50px;
  padding: 60px;
  text-align: center;
  background-color: white;
  img {
    display: block;
    margin: 20px auto;
    width: 200px;
    height: 200px;
    background-image: url(./components/avatar-cutter/imgs/empty.png);
    background-repeat: round;
  }
  .btn {
    display: block;
    margin: 0 auto;
    width: 200px;
    height: 40px;
    line-height: 40px;
    font-size: 24px;
    color: white;
    border-radius: 4px;
    text-align: center;
    box-sizing: border-box;
    background-color: #3D8AC7;
  }
}
</style>
<template>
  <section class="p-user-data">
    <img :src="imgSrc">
    <div class="btn" @click="showCutter=true">点击上传图片</div>
    <avatar-cutter v-if="showCutter" @cancel="showCutter = false" return-type="url" @enter="uploadAvatar"></avatar-cutter>
  </section>
</template>
<script>

import AvatarCutter from './components/avatar-cutter/avatar-cutter'

export default {
  components: {
    AvatarCutter,
  },
  data() {
    return {
      imgSrc: 'http://www.luckly-mjw.cn/baseSource/picture-avatar-03.png',
      showCutter: false, // 是否显示头像裁剪组件
      userInfo: {},
    }
  },

  methods: {
    // 上传裁剪好的头像
    uploadAvatar(src) {
      this.imgSrc = src
      this.showCutter = false
    },
  },
}

</script>
