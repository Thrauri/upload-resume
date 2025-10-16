<script setup>
import FileUploadPlaceholder from './components/FileUploadPlaceholder.vue'
import socialImg from './assets/社交描边矢量插画人物场景插画社交050930blue-01 1.svg'
</script>

<template>
  <div class="page">
    <section class="left-top">
      <h1 class="title">Finish!<br>
        Upload your resume</h1>
      <p class="subtitle">Upload your resume, the platform will help you parse and optimize, you can also skip this step</p>
    </section>
    <section class="right">
      <FileUploadPlaceholder />
    </section>
    <section class="left-bottom">
      <img :src="socialImg" alt="场景插画" />
    </section>
  </div>
  
</template>

<style scoped>

.page {
  display: grid;
  grid-template-columns: 4fr 6fr; /* 4:6 */
  grid-template-rows: auto 1fr;
  grid-template-areas:
    "left-top right"
    "left-bottom right";
  min-height: 100vh;
  background: #f8fbf9;
}

.left-top {
  grid-area: left-top;
  display: flex;
  flex-direction: column;
  gap: 16px;
  margin: 40px 32px;
}
.title {
  font-size: 28px;
  font-weight: 500;
  color: #0f172a;
  margin: 0;
}
.subtitle {
  color: #b7b7b7;
  margin: 0;
}
.left-bottom {
  grid-area: left-bottom;
  display: flex;
  align-items: flex-end;
}
.left-bottom img {
  width: 100%;
  max-width: 560px;
  height: auto;
  display: block;
}
.right {
  grid-area: right;
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 6vw 6vw 2vw 2vw;
  padding: 0;
}

@media (max-width: 920px) {
  .page {
    grid-template-columns: 1fr;
    grid-template-rows: auto auto auto;
    grid-template-areas:
      "left-top"
      "right"
      "left-bottom";
  }
  .right {
    margin: 0;
    padding-top: 0;
  }
}
</style>
