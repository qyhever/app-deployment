## Unified Deployment from Services

## 项目结构
- **app-deployment**: 中央部署仓库，包含 主 Nginx 入口，统一处理所有路由和 API 代理
- **pinco**: 博客项目，访问路径为 `/` 根路径
- **r3-admin-front**: 管理前端项目，访问路径为 `/r3-admin`
- **r3-admin-server**: 管理后端API服务，为r3-admin-front提供API支持，访问路径为 `/r3/api`

### 部署方案概述
多仓库（multi-repo）协同工作，通过一个统一的 GitHub Actions 工作流进行部署。

利用 GitHub Actions 的 `repository_dispatch` 事件来触发部署。当任何一个服务仓库有更新时，它会向这个中央仓库发送一个“信号”，触发统一的部署流程。

## test
13.30