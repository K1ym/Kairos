# Kairos 本地开发指南 (DEVELOPMENT)

> 本文档旨在帮助新加入的开发者快速搭建并运行 Kairos 项目。

## 先决条件

| 工具 | 版本要求 | 官网 |
| --- | --- | --- |
| Node.js | **18.x** 或更高 | https://nodejs.org/ |
| pnpm | **8.x** 或更高 | https://pnpm.io/ |
| Docker & Docker Compose | 最新稳定版 (用于本地 PostgreSQL) | https://www.docker.com/ |

> 建议使用 nvm 或 fnm 管理多版本 Node.js。

---

## 安装依赖

在项目根目录执行：

```bash
pnpm install
```

pnpm 将读取根 `package.json` 与 `turbo.json`，自动安装并链接所有 workspace 依赖。

---

## 环境变量

在项目根目录创建 `.env` 文件，并根据需要填写：

```dotenv
# 本地 PostgreSQL 连接字符串 (示例)
DATABASE_URL="postgresql://user:password@localhost:5432/kairos?schema=public"

# Google OAuth
GOOGLE_CLIENT_ID=""
GOOGLE_CLIENT_SECRET=""
```

> ⚠️ `.env` 已列入 `.gitignore`，请勿提交敏感信息。

---

## 本地开发

启动前端、后端及所有包的 `dev` 任务：

```bash
pnpm dev
```

脚本会调用 Turborepo，按 package `dev` 脚本并行执行：

- `apps/web` (Vite) – http://localhost:5173  
- `apps/api` (NestJS) – http://localhost:3000  
- 其他包将根据需要监听文件变化自动重启。

如需仅运行某个应用，可进入对应目录执行 `pnpm dev`。

---

祝你编码愉快！ 