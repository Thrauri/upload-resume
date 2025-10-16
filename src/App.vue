<script setup>
import FileUploadPlaceholder from './components/FileUploadPlaceholder.vue'
import socialImg from './assets/社交描边矢量插画人物场景插画社交050930blue-01 1.svg'
</script>

<template>
  <div class="page">
    <section class="left">
      <div class="left-top">
        <h1 class="title">上传您的简历</h1>
        <p class="subtitle">支持常见格式，稍后将接入实际上传能力。</p>
      </div>
      <div class="left-bottom">
        <img :src="socialImg" alt="场景插画" />
      </div>
    </section>
    <section class="right">
      <FileUploadPlaceholder />
    </section>
  </div>
  
</template>

<style scoped>
.page {
  display: flex;
  min-height: 100vh;
  background: #ffffff;
}
.left, .right {
  flex: 1;
  padding: 40px 32px;
  display: flex;
  flex-direction: column;
}
.left {
  gap: 24px;
}
.left-top {
  display: flex;
  flex-direction: column;
  gap: 8px;
}
.title {
  font-size: 28px;
  font-weight: 700;
  color: #0f172a;
  margin: 0;
}
.subtitle {
  color: #475569;
  margin: 0;
}
.left-bottom {
  margin-top: auto;
}
.left-bottom img {
  width: 100%;
  max-width: 560px;
  height: auto;
  display: block;
}
.right {
  align-items: center;
  justify-content: center;
  background: #f8fafc;
}

@media (max-width: 920px) {
  .page {
    flex-direction: column;
  }
  .right {
    padding-top: 0;
  }
}
</style>
