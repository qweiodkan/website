# 汤圆知识树屋

个人知识分享网站，包含博客、工具集合等内容。

## 项目结构

```
├── index.html              # 首页
├── blog/                   # Typecho 博客（服务器端）
├── tool/                   # 工具集合
│   ├── video-filter/       # 视频素材筛选工具
│   ├── video-segmenter/    # 视频分割工具
│   └── ...
├── .github/
│   └── workflows/
│       └── deploy.yml      # GitHub Actions 自动部署配置
└── nginx-default.conf      # Nginx 配置文件

```

## 技术栈

- **前端**: HTML/CSS/JavaScript (原生)
- **博客**: Typecho (PHP + SQLite)
- **服务器**: Ubuntu 22.04 + Docker
- **Web服务器**: Nginx (支持 Brotli 压缩)
- **CI/CD**: GitHub Actions

## 部署方式

### 自动部署

推送到 `main` 分支后，GitHub Actions 自动执行：

1. SSH 连接到服务器
2. 拉取最新代码
3. 重启 Nginx 容器
4. 验证部署成功

### 手动部署

```bash
# 服务器上执行
cd /opt/mywebsite
git pull origin main
docker restart nginx-site
```

## 服务器信息

- **IP**: 43.139.92.160
- **域名**: https://tangyuanzhp.top
- **Docker 容器**:
  - nginx-site (Nginx + Brotli)
  - typecho-php (PHP-FPM)

## 本地开发

```bash
# 克隆仓库
git clone https://github.com/tangyuan/website.git
cd website

# 本地预览（需要Web服务器）
python -m http.server 8000
```

## 维护说明

- SSL 证书自动续签（acme.sh）
- 系统更新: `sudo apt update && sudo apt upgrade -y`
- Docker 更新: `sudo apt upgrade docker-ce docker-ce-cli containerd.io`

## 作者

**汤圆**
- GitHub: [@tangyuan](https://github.com/tangyuan)
- 网站: https://tangyuanzhp.top