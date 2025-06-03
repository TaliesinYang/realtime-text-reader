# Local TXT Reader - Auto Scroll Fix

A modern web-based tool for reading and monitoring local text files with real-time updates and auto-scroll functionality.

## 🌟 Features

- **Real-time File Monitoring**: Automatically detects and displays new content as files are updated
- **Smart Auto-scroll**: Maintains scroll position at bottom, even when translation plugins modify content
- **Cross-browser Compatibility**: Works in Chrome/Edge (advanced mode) and Firefox/Safari (basic mode)
- **Translation Plugin Support**: Uses MutationObserver to handle DOM changes from translation extensions
- **Modern UI**: Clean, responsive design with system fonts
- **Performance Optimized**: Incremental file reading for large files

## 🚀 Live Demo

Visit the live demo: [https://yourusername.github.io/txt-reader/](https://yourusername.github.io/txt-reader/)

## 📦 Deployment

### GitHub Pages (Recommended)

1. **Fork or Clone this repository**
   ```bash
   git clone https://github.com/yourusername/txt-reader.git
   cd txt-reader
   ```

2. **Push to your GitHub repository**
   ```bash
   git add .
   git commit -m "Initial commit"
   git push origin main
   ```

3. **Enable GitHub Pages**
   - Go to your repository settings
   - Navigate to "Pages" section
   - Select "Deploy from a branch"
   - Choose "main" branch
   - Your site will be available at `https://yourusername.github.io/repository-name/`

### Other Static Hosting Platforms

- **Netlify**: Drag and drop the HTML file to [netlify.com](https://netlify.com)
- **Vercel**: Connect your GitHub repository to [vercel.com](https://vercel.com)
- **GitHub Codespaces**: Edit and preview directly in browser

## 🖥️ Browser Compatibility

| Browser | Support Level | Features Available |
|---------|---------------|-------------------|
| Chrome 86+ | ✅ Full | File monitoring, auto-refresh, MutationObserver |
| Edge 86+ | ✅ Full | File monitoring, auto-refresh, MutationObserver |
| Firefox | ⚠️ Basic | File upload only, no auto-refresh |
| Safari | ⚠️ Basic | File upload only, no auto-refresh |

## 🔧 Usage

### Advanced Mode (Chrome/Edge)
1. Click "Select and Monitor TXT File"
2. Choose a `.txt` file from your local system
3. The tool will monitor the file for changes every 1.5 seconds
4. New content automatically appears and scrolls to bottom

### Basic Mode (Firefox/Safari)
1. Click "Upload TXT File (Basic Mode)"
2. Select a `.txt` file
3. File content is displayed (no auto-refresh)
4. Refresh the page to load a new file

## 🛠️ Technical Details

### File System Access API
The advanced monitoring feature uses the modern [File System Access API](https://developer.mozilla.org/en-US/docs/Web/API/File_System_Access_API), which provides:
- Direct file system access without uploads
- Real-time file change detection
- Incremental content reading

### MutationObserver Integration
Handles DOM modifications from browser extensions (especially translation tools):
```javascript
const observer = new MutationObserver(() => {
    // Auto-scroll after DOM changes
    scrollToBottom(contentElement);
});
```

### Performance Optimizations
- **Incremental Reading**: Only reads new file content
- **Debounced Scrolling**: Prevents excessive scroll operations
- **Memory Management**: Proper cleanup of observers and intervals

## 📁 File Structure

```
txt-reader/
├── readtxt.html              # Original version
├── readtxt-improved.html     # Enhanced version with fallback
├── README.md                 # This file
└── .gitignore               # Git ignore file
```

## 🎯 Use Cases

- **Log File Monitoring**: Watch server logs, application logs in real-time
- **Development**: Monitor build outputs, test results
- **Documentation**: Read continuously updated documentation
- **Translation**: Use with browser translation extensions for foreign language texts

## 🔒 Privacy & Security

- **100% Client-side**: No data is sent to any server
- **Local File Access**: Files never leave your computer
- **No Tracking**: No analytics or tracking scripts
- **Open Source**: Full source code available for inspection

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch: `git checkout -b feature-name`
3. Commit your changes: `git commit -am 'Add feature'`
4. Push to the branch: `git push origin feature-name`
5. Submit a pull request

## 📝 License

This project is open source and available under the [MIT License](LICENSE).

## 🐛 Known Issues

- Large files (>100MB) may cause performance issues
- File encoding must be UTF-8 for proper display
- Some antivirus software may block File System Access API

## 🔮 Future Enhancements

- [ ] Support for more file formats (CSV, JSON, XML)
- [ ] Search functionality within files
- [ ] Bookmark/navigation features
- [ ] Dark mode theme
- [ ] File comparison tools
- [ ] Export functionality

## 📞 Support

If you encounter any issues or have questions:
- Open an issue on GitHub
- Check the browser console for error messages
- Ensure your browser supports the required APIs

## 🔧 详细使用教程

### 🚀 快速开始

#### 方法一：在线使用（推荐）
1. 访问在线版本：[https://yourusername.github.io/txt-reader/](https://yourusername.github.io/txt-reader/)
2. 根据你的浏览器选择对应模式

#### 方法二：本地使用
1. 下载 `readtxt-improved.html` 文件
2. 双击文件在浏览器中打开
3. 开始使用

### 📖 详细操作指南

#### Chrome/Edge 用户（高级模式）

**第一步：选择文件**
1. 点击蓝色按钮 "Select and Monitor TXT File"
2. 在弹出的文件选择器中，浏览到你的文本文件
3. 选择一个 `.txt` 文件并点击"打开"

**第二步：开始监控**
- 文件内容会立即显示在页面中
- 状态栏显示：`File "filename.txt" has been fully loaded. Size: XXX bytes.`
- 工具会每1.5秒自动检查文件是否有更新

**第三步：实时查看更新**
- 当文件有新内容时，页面会自动滚动到底部显示最新内容
- 状态栏会显示：`File "filename.txt" has new content. Current size: XXX bytes.`

#### Firefox/Safari 用户（基础模式）

**第一步：上传文件**
1. 页面会自动显示兼容性提示
2. 点击灰色按钮 "Upload TXT File (Basic Mode)"
3. 选择你的 `.txt` 文件

**第二步：查看内容**
- 文件内容会一次性加载并显示
- 状态栏显示：`File "filename.txt" loaded successfully. Refresh page to load a new file.`

**注意**：基础模式不支持实时监控，需要手动刷新页面来加载新文件

### 💡 实际使用场景

#### 场景1：监控日志文件
```bash
# 假设你有一个持续更新的日志文件
tail -f /var/log/application.log > ~/Desktop/app.log
```
1. 在工具中选择 `~/Desktop/app.log`
2. 每当有新的日志条目时，页面会自动显示并滚动到最新内容

#### 场景2：开发调试
```bash
# 监控构建输出
npm run build > build-output.txt 2>&1
```
1. 选择 `build-output.txt` 文件
2. 实时查看构建进度和错误信息

#### 场景3：配合翻译插件使用
1. 选择一个外语文档
2. 启用浏览器翻译插件（如沉浸式翻译）
3. 工具会自动处理翻译插件对页面的修改，保持滚动位置

### 🔧 高级功能

#### 自动滚动机制
- **智能检测**：使用 MutationObserver 监控DOM变化
- **防抖处理**：150ms防抖延迟，避免频繁滚动
- **翻译兼容**：自动适应翻译插件的内容修改

#### 性能优化
- **增量读取**：只读取文件新增部分，不重复读取整个文件
- **内存管理**：自动清理观察器和定时器，防止内存泄漏
- **错误恢复**：文件被删除或移动时自动提示重新选择

### ⚠️ 常见问题与解决方案

#### 问题1：文件选择后没有反应
**解决方案**：
- 确保使用Chrome 86+或Edge 86+浏览器
- 检查文件是否为UTF-8编码的.txt文件
- 查看浏览器控制台是否有错误信息

#### 问题2：文件更新但页面没有刷新
**解决方案**：
- 确认文件确实被修改（检查文件修改时间）
- 某些编辑器可能使用临时文件，尝试使用其他编辑器
- 检查文件是否被其他程序锁定

#### 问题3：大文件加载缓慢
**解决方案**：
- 建议文件大小控制在50MB以内
- 对于超大文件，考虑使用 `tail` 命令提取最新部分
- 清理浏览器缓存释放内存

#### 问题4：中文或特殊字符显示乱码
**解决方案**：
- 确保文件保存为UTF-8编码
- 使用支持UTF-8的文本编辑器（如VS Code、Notepad++）
- 避免使用Windows记事本保存中文文件

### 📱 移动设备使用

#### iOS Safari
- 支持基础文件上传模式
- 可以从iCloud Drive或其他云存储选择文件
- 建议使用横屏模式获得更好的阅读体验

#### Android Chrome
- 支持完整的高级监控模式
- 可以选择本地存储或云存储中的文件
- 支持所有桌面版功能

### 🎯 最佳实践

1. **文件命名**：使用英文文件名避免编码问题
2. **文件大小**：保持文件在合理大小（<50MB）
3. **编码格式**：始终使用UTF-8编码
4. **浏览器选择**：优先使用Chrome或Edge获得最佳体验
5. **网络环境**：本地文件访问不需要网络连接

### 🔄 版本更新

当工具有新版本时：
1. 刷新页面获取最新版本
2. 如果使用本地文件，重新下载最新的HTML文件
3. GitHub Pages版本会自动更新

---

💡 **提示**：首次使用建议先用一个小的测试文件熟悉功能，然后再用于重要的日志监控任务。

---

⭐ **Star this repository if you find it useful!** 