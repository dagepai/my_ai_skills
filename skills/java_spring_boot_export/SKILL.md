-在创建或修改 Spring Boot 项目代码时，按团队约定的分层结构、异常处理、日志规范进行开发。

# Java Spring Boot 开发规范
## 分层结构
- Controller 层：只做参数校验、调用 Service、返回 DTO
- Service 层：业务逻辑，事务边界
- Repository/Mapper 层：数据库访问
- 禁止跨层直接访问（如 Controller 直接调 Repository）
## 命名规范
- 类名使用 PascalCase，如 UserService
- 方法名使用 camelCase，如 getUserById
- 常量全大写下划线分隔，如 MAX_RETRY_COUNT
## 异常处理
- 不在代码中吞掉异常
- 使用统一的业务异常类型（如 BusinessException）
- 在 Controller 层统一异常处理与错误响应格式
## 日志规范
- 关键业务入口、出口必须记录日志（INFO）
- 异常情况必须记录异常堆栈（ERROR）
- 日志中避免输出敏感信息
## 步骤
1. 分析新增/修改涉及的类和接口
2. 确保分层正确、调用路径清晰
3. 检查异常处理是否符合统一规范
4. 补齐必要的日志记录