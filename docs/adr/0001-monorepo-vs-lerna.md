# ADR 0001：选择 Turborepo 作为 Monorepo 解决方案

日期：2025-06-22  
状态：Accepted

## Context
Kairos 前后端及共享库需在同一代码仓库内协作，历史上主流方案有 Lerna、Nx、Turborepo 等。
我们特别关注：
1. TypeScript + React + NestJS 生态的原生支持  
2. 构建/缓存性能  
3. CI/CD 复杂度与团队学习成本

## Decision
采用 **Turborepo** 作为 Monorepo 工具。理由：
- Vite / Next / Nest 等现代框架默认提供官方示例，开箱即用  
- Remote Caching 与增量构建简单易用  
- 生态与社区活跃，Meta / Vercel 大厂背书  
- 配置文件直观（turbo.json），降低新成员上手门槛

## Consequences
### Positive
- 一致的构建管道与任务缓存，节省 CI 时间  
- 跨包引用能自动保持 TypeScript 类型安全  
- 后续如需拆分微服务，可在同一仓库继续演进

### Negative
- 对旧版 Node (<14) 支持欠佳（可接受）  
- 缓存存储在云端需额外配置（暂规划使用 Vercel Remote Cache）

## Alternatives Considered
- **Lerna**：维护活跃度下降，需搭配 Yarn Workspaces + 自行配置缓存  
- **Nx**：功能强大但学习曲线较陡，配置更重 