# hexo-hmm

基于 **Hexo + Butterfly** 的中文博客项目，仓库地址：<https://github.com/hmmzhtx/Hexo_HMM.git>

当前默认配置：

- 站点标题：`hexo-hmm`
- 语言：`zh-CN`
- 时区：`Asia/Shanghai`
- 默认主题：`butterfly`
- Cloudflare Pages 项目名：`hexo-hmm`

## 目录说明

```text
.
├─ _config.yml                 # Hexo 主配置
├─ _config.butterfly.yml       # Butterfly 主题覆盖配置
├─ package.json                # 依赖和脚本
├─ scaffolds/                  # 文章模板
├─ source/                     # 站点源码
│  ├─ _posts/                  # 博客文章
│  ├─ categories/              # 分类页
│  └─ tags/                    # 标签页
└─ public/                     # 构建输出（执行 build 后生成）
```

## 本地运行

首次或依赖变化后：

```bash
npm install --no-bin-links
```

启动本地预览：

```bash
npm run server
```

默认访问地址：<http://localhost:4000>

生成静态文件：

```bash
npm run build
```

清理缓存与旧构建：

```bash
npm run clean
```

## 创建文章

新建一篇文章：

```bash
npm run new -- "我的第一篇文章"
```

文章会生成在：

```text
source/_posts/
```

写完后本地预览：

```bash
npm run server
```

## GitHub 推送

当前仓库远程地址已绑定：

```bash
git remote -v
```

推送流程：

```bash
git add .
git commit -m "feat: 初始化 Hexo 博客并配置 Butterfly"
git push -u origin main
```

如果只是日常发文更新：

```bash
git add .
git commit -m "docs: 发布新文章"
git push
```

## Cloudflare Pages 配置

Pages 项目名：`hexo-hmm`

在 Cloudflare Pages 中连接 GitHub 仓库 `hmmzhtx/Hexo_HMM` 时，建议填写：

- **Framework preset**: `Hexo`
- **Build command**: `npm run build`
- **Build output directory**: `public`
- **Node.js version**: `20` 或更高

如果界面没有 Hexo 预设，也可以手动填：

- Build command：`npm install --no-bin-links && npm run build`
- Output directory：`public`

## 建议的后续自定义

你可以按需继续修改：

- `_config.yml`：站点标题、描述、域名
- `_config.butterfly.yml`：导航、社交链接、首页副标题
- `source/_posts/`：开始写文章

## 说明

由于项目位于 Windows 挂载盘 `/mnt/e/博客`，安装依赖时使用了 `--no-bin-links`，避免 `node_modules/.bin` 符号链接在该文件系统下失败。因此 `package.json` 中的脚本已改为直接调用本地 Hexo CLI，可直接 `npm run build` / `npm run server`。
