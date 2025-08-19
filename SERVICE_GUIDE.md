# 🚀 Jekyll 本地服务器使用指南

## 📋 概述
本指南将帮助你启动和终止本地Jekyll服务器，实现网站实时预览功能。

## 🎯 快速开始

### 启动服务器
```bash
# 进入项目目录
cd /Users/DannyWang/VSCodeProject/DannyWang1922.github.io

# 启动Jekyll服务器（包含实时重载功能）
bundle exec jekyll serve --livereload
```

### 访问网站
启动成功后，在浏览器中打开：
- **本地地址**: `http://localhost:4000`
- **网络地址**: `http://0.0.0.0:4000` (局域网内其他设备可访问)

### 停止服务器
在运行服务器的终端中按：
- **macOS/Linux**: `Ctrl + C`
- **Windows**: `Ctrl + C`

## 🔧 详细配置选项

### 基础启动命令
```bash
# 基础启动（仅本地访问）
bundle exec jekyll serve

# 启用实时重载（推荐）
bundle exec jekyll serve --livereload

# 允许局域网访问
bundle exec jekyll serve --livereload --host 0.0.0.0

# 指定端口（默认4000）
bundle exec jekyll serve --livereload --port 8080

# 完整配置示例
bundle exec jekyll serve --livereload --host 0.0.0.0 --port 4000 --drafts
```

### 常用参数说明
- `--livereload`: 启用实时重载，文件修改后自动刷新浏览器
- `--host 0.0.0.0`: 允许局域网内其他设备访问
- `--port 4000`: 指定服务器端口（默认4000）
- `--drafts`: 包含草稿文件
- `--future`: 包含未来日期的文章
- `--incremental`: 增量构建，提高构建速度

## 📱 实时预览功能

### 工作原理
1. **文件监控**: Jekyll监控项目文件变化
2. **自动构建**: 检测到变化时自动重新构建
3. **浏览器刷新**: 通过LiveReload自动刷新浏览器

### 支持的文件类型
- ✅ Markdown文件 (`.md`)
- ✅ HTML文件 (`.html`)
- ✅ CSS文件 (`.css`, `.scss`)
- ✅ JavaScript文件 (`.js`)
- ✅ 图片文件 (`.jpg`, `.png`, `.gif`等)
- ✅ 配置文件 (`_config.yml`)

## 🚨 故障排除

### 常见问题

#### 1. 端口被占用
```bash
# 查看端口占用
lsof -i :4000

# 杀死占用进程
kill -9 <PID>

# 或使用其他端口
bundle exec jekyll serve --port 8080
```

#### 2. 权限问题
```bash
# 确保在正确的目录
pwd
# 应该显示: /Users/DannyWang/VSCodeProject/DannyWang1922.github.io

# 检查文件权限
ls -la
```

#### 3. 依赖问题
```bash
# 重新安装依赖
bundle install

# 清理缓存
bundle clean --force
```

### 错误日志
如果遇到问题，查看终端输出的错误信息，常见错误包括：
- 语法错误
- 配置文件问题
- 依赖版本不兼容

## 🔄 工作流程建议

### 开发阶段
1. **启动服务器**: `bundle exec jekyll serve --livereload`
2. **编辑文件**: 修改任何项目文件
3. **实时预览**: 浏览器自动刷新显示最新内容
4. **测试功能**: 验证修改效果

### 部署阶段
1. **停止服务器**: `Ctrl + C`
2. **提交代码**: `git add . && git commit -m "更新说明"`
3. **推送到GitHub**: `git push origin main`
4. **等待部署**: 2-5分钟后访问 `https://dannywang1922.github.io`

## 📚 相关命令

### 构建命令
```bash
# 仅构建，不启动服务器
bundle exec jekyll build

# 构建到指定目录
bundle exec jekyll build --destination ./_site

# 清理构建文件
bundle exec jekyll clean
```

### 检查命令
```bash
# 检查语法
bundle exec jekyll doctor

# 检查依赖
bundle check

# 查看Jekyll版本
bundle exec jekyll --version
```

## 🌟 最佳实践

1. **开发时使用本地服务器**: 快速预览和调试
2. **部署前本地测试**: 确保所有功能正常
3. **定期更新依赖**: `bundle update`
4. **使用版本控制**: 每次修改后及时提交
5. **备份重要文件**: 特别是配置文件

## 📞 技术支持

如果遇到问题：
1. 查看终端错误信息
2. 检查Jekyll官方文档
3. 搜索GitHub Issues
4. 检查网络连接

---

**提示**: 首次启动可能需要几分钟时间，请耐心等待。后续启动会更快。

