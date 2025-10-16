# upload-resume（简历上传界面）

一个使用 Vue 3 + Vite + Element Plus 构建的简历上传页面。界面包含标题与说明、上传组件以及插画图片。

## 功能特性
- 响应式布局：小屏幕自动切换为上下结构：标题 → 上传组件 → 图片
- 使用 Element Plus 组件：Upload（拖拽上传）、Button、Steps（步骤进度）
- 上传交互：
  - 未选择文件点击finish给出“请上传文件”提示
  - 点击Upload组件打开文件选择框，或拖拽文件到Upload组件，并显示上传文件名
  - 文件上传完成后点击finish提示“上传成功”，并将下方step组件推进到第三步

## 技术栈

- Vue 3 + `<script setup>`
- Vite
- Element Plus（UI 组件库）

## 开发与运行

```bash
npm install
npm run dev
```

构建生产包：

```bash
npm run build
```

## 目录结构

```text
upload-resume/
  ├─ src/
  │  ├─ App.vue                  # 页面布局与整体样式
  │  ├─ main.js                  # 应用入口，注册 Element Plus & Pinia & Router
  │  ├─ components/
  │  │  └─ FileUploadPlaceholder.vue  # 右侧上传组件（Element Plus 版）
  │  ├─ assets/
  │  │  ├─ Vector.svg            # 上传区域图标
  │  │  └─ 社交描边...blue-01 1.svg # 左侧插画
  │  ├─ router/
  │  └─ stores/
  ├─ index.html
  ├─ vite.config.js
  └─ README.md
```

## 主要页面说明（App.vue）

- 使用 CSS Grid 设置两列：`grid-template-columns: 4fr 6fr`
- 三个区域：
  - `left-top`：标题与说明文案
  - `right`：上传组件（卡片白底、圆角、阴影）
  - `left-bottom`：插画图片
- 响应式：小屏幕下使用单列顺序“标题 → 上传组件 → 图片”

## 上传组件说明（FileUploadPlaceholder.vue）

- 使用 `el-upload` 开启 `drag` 模式，禁用自动上传（`:auto-upload="false"`）
- Button使用 `el-button`，两按钮等宽，左侧禁用；右侧点击触发校验与模拟上传
- Steps使用 `el-steps`，`finish-status="success"`，并通过样式覆盖：
  - 完成与当前步骤为蓝色 `#3B82F6`
  - 未完成步骤为灰色 `#9CA3AF`
- 交互提示：
  - 未选择文件：`ElMessage.warning('请上传文件')`
  - 上传完成：`ElMessage.success('上传成功')`

