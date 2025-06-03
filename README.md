# 🌟 Local TXT Reader - 实时文件阅读器

一个现代化的本地TXT文件实时监控和阅读工具，采用苹果风格的优雅设计和极光呼吸背景效果。

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Browser Support](https://img.shields.io/badge/browser-Chrome%2086%2B%20%7C%20Edge%2086%2B-green.svg)
![Version](https://img.shields.io/badge/version-2.0-brightgreen.svg)

## ✨ 设计特色

### 🎨 Apple风格美学
- **极光呼吸背景**：灵感来自苹果设计哲学的优雅极光效果
- **玻璃拟态设计**：半透明组件配合背景模糊效果
- **流畅动画**：8-12秒缓慢呼吸动画，营造宁静氛围
- **双主题支持**：亮色/暗色主题无缝切换

### 🌈 视觉效果
- **亮色主题**：柔和的蓝色、紫色、绿色极光渐变
- **暗色主题**：深邃的夜空配合更强烈的极光色彩
- **呼吸动画**：背景随时间轻柔地缩放和移动
- **模糊滤镜**：40-60px模糊效果创造梦幻感

## 🚀 核心功能

### 📁 智能文件监控
- **File System Access API**：现代浏览器原生文件访问
- **实时更新检测**：每1.5秒自动检查文件变化
- **增量读取**：只读取新增内容，提升性能
- **自动滚动**：始终显示最新内容

### 🔧 高级特性
- **MutationObserver**：兼容翻译插件的DOM修改
- **防抖处理**：150ms延迟避免频繁滚动
- **错误恢复**：文件丢失或权限问题自动处理
- **兼容模式**：Firefox/Safari降级文件上传支持

## 🎯 使用场景

- **开发调试**：实时监控日志文件
- **文档编写**：预览Markdown或文本文件
- **数据分析**：观察实时数据输出
- **学习笔记**：动态查看学习进度

## 🌐 浏览器兼容性

| 浏览器 | 版本要求 | 功能支持 |
|--------|----------|----------|
| Chrome | 86+ | ✅ 完整功能 |
| Edge | 86+ | ✅ 完整功能 |
| Firefox | 任意版本 | 🔄 基础模式 |
| Safari | 任意版本 | 🔄 基础模式 |

## 📦 部署指南

### GitHub Pages 部署

1. **Fork 仓库**
   ```bash
   git clone https://github.com/yourusername/realtimeReading.git
   cd realtimeReading
   ```

2. **启用 GitHub Pages**
   - 进入仓库设置 → Pages
   - 选择 `main` 分支作为源
   - 保存设置

3. **访问应用**
   ```
   https://yourusername.github.io/realtimeReading/readtxt-improved.html
   ```

### 本地运行

```bash
# 克隆仓库
git clone https://github.com/yourusername/realtimeReading.git

# 进入目录
cd realtimeReading

# 使用任意HTTP服务器
python -m http.server 8000
# 或
npx serve .

# 访问 http://localhost:8000/readtxt-improved.html
```

## 🎮 使用教程

### 基础操作

1. **选择文件**
   - 点击"Select and Monitor TXT File"按钮
   - 选择要监控的.txt文件
   - 授予浏览器文件访问权限

2. **主题切换**
   - 点击左上角的主题切换按钮 🌓
   - 支持亮色/暗色主题
   - 设置会自动保存到本地存储

3. **实时监控**
   - 文件内容会自动更新
   - 新内容会高亮显示
   - 自动滚动到底部

### 高级技巧

- **快捷键**：`Ctrl+R` 刷新页面重新选择文件
- **多文件**：可以在多个标签页中监控不同文件
- **性能优化**：大文件会自动启用增量读取模式

## 🛠️ 技术架构

### 前端技术栈
- **原生JavaScript**：无框架依赖，轻量高效
- **CSS3动画**：硬件加速的流畅动画
- **File System Access API**：现代文件访问接口
- **MutationObserver**：DOM变化监听

### 设计模式
- **响应式设计**：适配各种屏幕尺寸
- **渐进增强**：优雅降级到兼容模式
- **无障碍访问**：支持键盘导航和屏幕阅读器

## 🎨 自定义配置

### 修改动画速度
```css
/* 调整呼吸动画周期 */
.unified-breathing-background::before {
    animation: auroraBreath 8s ease-in-out infinite; /* 改为6s或10s */
}
```

### 调整极光颜色
```css
/* 自定义极光色彩 */
radial-gradient(ellipse 800px 400px at 30% 20%, 
    rgba(59, 130, 246, 0.15) 0%, /* 蓝色 */
    transparent 50%
)
```

### 修改透明度
```css
/* 调整组件透明度 */
.page-header {
    background: rgba(255, 255, 255, 0.3); /* 0.1-0.9 */
}
```

## 🔧 故障排除

### 常见问题

**Q: 文件选择后没有内容显示？**
A: 确保选择的是.txt格式文件，并检查文件权限。

**Q: 自动更新不工作？**
A: 检查浏览器是否支持File System Access API，或切换到兼容模式。

**Q: 极光背景不显示？**
A: 确保浏览器支持CSS3动画和模糊滤镜效果。

**Q: 性能问题？**
A: 大文件会自动启用增量读取，如仍有问题可尝试刷新页面。

### 调试模式

打开浏览器开发者工具，在控制台中输入：
```javascript
// 查看当前文件状态
console.log('File handle:', fileHandle);
console.log('Last position:', lastReadPosition);

// 手动触发更新
checkAndUpdateFile();
```

## 🤝 贡献指南

欢迎提交Issue和Pull Request！

### 开发环境设置
```bash
git clone https://github.com/yourusername/realtimeReading.git
cd realtimeReading
# 直接在浏览器中打开 readtxt-improved.html 进行开发
```

### 提交规范
- `feat:` 新功能
- `fix:` 修复bug
- `docs:` 文档更新
- `style:` 样式调整
- `refactor:` 代码重构

## 📄 许可证

本项目采用 [MIT 许可证](LICENSE)。

## 🙏 致谢

- 设计灵感来自 Apple 的优雅美学
- 感谢现代浏览器对 File System Access API 的支持
- 特别感谢所有贡献者和用户的反馈

---

**享受优雅的文件阅读体验！** ✨ 