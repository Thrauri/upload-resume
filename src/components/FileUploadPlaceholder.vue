<template>
  <div class="upload-placeholder">
    <div class="box">
      <div class="icon">⬆</div>
      <div class="title">文件上传</div>
      <div class="desc">这里是占位上传组件</div>
    </div>
  </div>
</template>

<script setup>
</script>

<style scoped>
.upload-placeholder {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 100%;
  height: 100%;
}
.box {
  width: 80%;
  max-width: 420px;
  min-height: 240px;
  border: 2px dashed #cbd5e1;
  border-radius: 12px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 8px;
  background: #f8fafc;
}
.icon {
  font-size: 28px;
  line-height: 1;
}
.title {
  font-weight: 600;
}
.desc {
  color: #64748b;
  font-size: 14px;
}
</style>


