# Contributing to Kairos

感谢贡献！请遵循以下流程：

1. **Fork & Branch**  
   新功能使用 `feat/<scope>-<short-desc>`  
   修复使用 `fix/<scope>-<short-desc>`

2. **Commit Message — Conventional Commits**
   ```
   feat(onboarding): add OAuth error boundary
   fix(dashboard): correct goal hierarchy query
   docs(adr): create 0002-database-strategy
   ```
   结构：`type(scope): description`

3. **Pull Request**  
   - 填写变更概要、相关 Issue 或 ADR  
   - 如更改公共 API / 配置，必须同步更新文档

4. **Changelog**  
   - 在 `CHANGELOG.md` 的 `[Unreleased]` 中添加条目  
   - 使用 Added / Changed / Fixed / Removed 之一

5. **Code Style**  
   - 通过 `npm run lint && npm run test`  
   - 保持单元测试覆盖率不下降 