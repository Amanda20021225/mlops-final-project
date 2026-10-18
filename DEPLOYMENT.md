# 部署说明

本项目的部署通过 GitHub Actions 自动完成。

- **Staging 环境**：当代码合并到 `staging` 分支时，流水线会从 `secrets.STAGING_ENV` 注入环境变量，并构建 `heartguard:staging` 镜像。
- **Production 环境**：当代码合并到 `main` 分支时，流水线会从 `secrets.PROD_ENV` 注入环境变量，并构建 `heartguard:prod` 镜像。
- **镜像构建**：统一通过根目录的 `Dockerfile` 构建，确保依赖一致。