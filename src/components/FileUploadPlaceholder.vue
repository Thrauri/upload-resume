<template>
  <div class="upload-container">
    <div class="upload-card">
      <!-- 标题 -->
      <div class="upload-header">
        <h2 class="upload-title">Upload file</h2>
      </div>

      <!-- ElementPlus 上传组件 -->
      <el-upload
        ref="uploadRef"
        class="upload-demo"

        drag
        :auto-upload="false"
        :on-change="handleFileChange"
        :on-remove="handleFileRemove"
        :file-list="fileList"
        :limit="1"
        accept=".pdf,.doc,.docx"
      >
        <div class="upload-content">
          <div class="upload-icon">
            <img :src="VectorIcon" alt="Upload icon" />
          </div>
          <div class="upload-text">
            Drag your resume file to this area, or click on the area to select the appropriate file to upload
          </div>
        </div>
      </el-upload>

       <!-- ElementPlus 按钮组 -->
       <div class="button-group">
         <el-button type="primary" :disabled="true" class="button">
           Last step
         </el-button>
         <el-button
           type="primary"
           @click="uploadFile"
           :loading="isUploading"
           class="button"
         >
           Finish
         </el-button>
       </div>

      <!-- ElementPlus 步骤条 -->
      <div class="steps-section">
        <el-steps :active="currentStep" finish-status="success" align-center>
          <el-step/>
          <el-step/>
          <el-step/>
        </el-steps>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import { ElMessage } from 'element-plus'
import VectorIcon from '../assets/Vector.svg'

const uploadRef = ref(null)
const fileList = ref([])
const isUploading = ref(false)
const currentStep = ref(2) // 初始完成第二步
const uploadSuccess = ref(false)

const handleFileChange = (file, fileListParam) => {
  fileList.value = fileListParam
}

const handleFileRemove = (file, fileListParam) => {
  fileList.value = fileListParam
}

const uploadFile = async () => {
  if (fileList.value.length === 0) {
    ElMessage.warning('请上传文件')
    return
  }

  isUploading.value = true

  // 模拟上传过程
  await new Promise(resolve => setTimeout(resolve, 1500))

  // 完成第三步
  currentStep.value = 3
  uploadSuccess.value = true
  isUploading.value = false

  ElMessage.success('上传成功')
}
</script>

<style scoped>
.upload-container {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 100%;
  height: 100%;
}

.upload-card {
  box-sizing: border-box;
  background: white;
  border-radius: 16px;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
  padding: 32px 72px;
  height: 100%;
  width: 100%;
  max-width: 960px;
  display: flex;
  flex-direction: column;
  gap: 48px;
}

.upload-header {
  text-align: left;
}

.upload-title {
  font-size: 24px;
  font-weight: 700;
  color: #1f2937;
  margin: 0 0 8px 0;
}

.upload-demo{
  flex: 1;
}



:deep(.el-upload-dragger) {
  border: 2px dashed #3B82F6 !important;
  border-radius: 12px !important;
  background: #f2faff !important;
  display: flex;
  align-items: center;
  justify-content: center;
  width: 100% !important;
  height: 100% !important;
  padding: 40px 60px !important;
}

:deep(.el-upload-dragger:hover) {
  border-color: #3B82F6 !important;
  background: #eff6ff !important;
}


:deep(.el-upload.el-upload--text.is-drag){
  height: 100%
}

.upload-content {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 12px;
}

.upload-icon {
  width: 48px;
  height: 48px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.upload-icon img {
  width: 100%;
  height: 100%;
  opacity: 0.7;
}

.upload-text {
  color: #9ca3af;
  font-size: 14px;
  text-align: center;
}

.button-group {
  margin: 0 16px;
  display: flex;
  gap: 12px;
  justify-content: center;
}

.button {
  min-height: 40px;
  min-width: 200px;
}

.steps-section {
  display: flex;
  flex-direction: column;
  gap: 16px;
}

.steps-label {
  font-size: 14px;
  font-weight: 600;
  color: #374151;
  text-align: center;
}

/* ElementPlus Steps 组件样式调整 */
:deep(.el-steps) {
  margin: 0;
}

:deep(.el-step__title) {
  font-size: 12px;
}

:deep(.el-step__icon.is-text) {
  background-color: #3B82F6 !important;
  border-color: #3B82F6 !important;
  color: #ffffff !important;
}


:deep(.el-step__head.is-success) {
  color: #3B82F6 !important;
  border-color: #3B82F6 !important;
}

:deep(.el-step__line) {
  background-color: #E5E7EB !important;
  height: 2px !important;
}

:deep(.el-step__line-inner) {
  background-color: #3B82F6 !important;
  height: 2px !important;
}
</style>



