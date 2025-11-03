# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## 项目概述

这是一个需求分析培训演示文稿项目，使用纯HTML5 + CSS3 + 原生JavaScript构建的单页面幻灯片应用。项目采用玻璃拟态设计风格，专注于程序员AI辅助需求分析培训内容。

## 核心架构

### 技术栈
- **前端**: 纯HTML5 + CSS3 + 原生JavaScript（无外部依赖）
- **设计**: 玻璃拟态风格 + 响应式布局
- **部署**: 静态文件，可直接在浏览器中打开

### 主要文件
- `从程序员到AI应用工程师 - 需求分析与沟通技巧培训.html` - 主演示文稿（1238行）
- `程序员利用AI工具做需求分析和沟通的完整流程指南.txt` - 培训文档（1001行）
- `*.docx` - Word格式培训文档

## 开发命令

### 运行项目
```bash
# 直接在浏览器中打开HTML文件
open "从程序员到AI应用工程师 - 需求分析与沟通技巧培训.html"

# 或使用本地服务器（推荐）
python3 -m http.server 8000
# 然后访问 http://localhost:8000
```

### 开发工具
```bash
# 实时预览（使用VS Code Live Server扩展）
# 右键HTML文件 -> "Open with Live Server"

# 代码格式化
# 使用VS Code内置格式化或Prettier扩展
```

## 代码架构

### HTML结构
- **容器**: `.presentation-container` - 主演示容器
- **幻灯片**: `.slide` - 每个幻灯片页面
- **状态管理**: `active` 类控制当前显示的幻灯片

### CSS架构
```css
/* 核心CSS变量 */
:root {
    --bg-color: #050a1b;         /* 深空蓝背景 */
    --accent-color: #00f2a1;     /* 科技薄荷绿 */
    --text-color: #e0f7fa;       /* 浅色文本 */
    --glass-bg: rgba(20, 30, 60, 0.75); /* 玻璃效果 */
}
```

**反滚动设计模式**:
- 全局禁止滚动: `body { overflow: hidden }`
- 局部可滚动区域: `.card-content { overflow-y: auto }`
- 固定高度容器: `height: calc(100vh - 2 * 5vh)`

### JavaScript架构
```javascript
// 状态管理
let currentSlide = 0;
const slides = document.querySelectorAll('.slide');

// 核心功能
function showSlide(index) // 幻灯片切换
function toggleFullScreen() // 全屏切换
```

### 组件类型
1. **封面页**: `.bg-cover` - 全屏背景图
2. **图文Slider**: `.card-with-aside-image` - 左文右图布局
3. **卡片阵列**: `.multi-card-container` - 多卡片网格布局
4. **代码展示**: `.code-container` - 代码高亮容器

## 交互功能

### 键盘快捷键
- `←` / `→` - 上一张/下一张幻灯片
- `Space` - 下一张幻灯片
- `Esc` - 退出全屏模式

### 导航控制
- 底部导航按钮
- 页码显示 (`currentSlide + 1` / `slides.length`)
- 全屏模式切换

## 内容结构

培训内容涵盖：
- 需求分析基础理论
- AI辅助需求分析方法
- 5W2H分析法
- KANO模型
- 需求沟通技巧
- 实战案例演示

## 修改指南

### 添加新幻灯片
1. 在HTML中添加新的 `.slide` 元素
2. 更新JavaScript中的幻灯片总数逻辑
3. 确保遵循现有的CSS类命名规范

### 样式修改
- 修改CSS变量来调整主题色彩
- 保持玻璃拟态效果的一致性
- 确保响应式设计兼容性

### 内容更新
- 直接编辑HTML中的文本内容
- 更新对应的Word文档保持同步
- 注意保持中文内容的准确性

## 注意事项

- 项目无构建系统，直接编辑HTML文件
- 无外部依赖，保持轻量级特性
- 遵循KISS原则，避免过度复杂化
- 确保跨浏览器兼容性
- 保持中文内容的专业性和准确性