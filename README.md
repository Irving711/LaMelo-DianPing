# LaMelo-Dianping

基于 Spring Boot 的本地生活点评后端，包含用户登录、店铺查询与缓存、博客互动、关注 Feed 和优惠券秒杀等功能。项目集成 Redis、Redisson、RabbitMQ、Sentinel 和 JWT。

## 运行环境

- JDK 8
- Maven
- MySQL、Redis、RabbitMQ

先创建 `hmdp` 数据库并导入 `src/main/resources/db/hmdp.sql`，再按本机环境配置服务连接信息。

## 本地配置

连接密码和 JWT 签名密钥不放在版本库中。可将 `application-local.example.yaml` 复制为项目根目录下的 `application-local.yaml`，再填写本机配置；该本地文件已加入 `.gitignore`。也可以通过环境变量配置：

- `HMDP_DB_USERNAME`、`HMDP_DB_PASSWORD`
- `HMDP_REDIS_PASSWORD`
- `HMDP_RABBITMQ_USERNAME`、`HMDP_RABBITMQ_PASSWORD`
- `HMDP_JWT_SECRET`（必填，使用随机且足够长的值）

默认使用 `local` 配置组，服务地址和端口见 `src/main/resources/application.yaml`。准备好依赖服务与配置后，可执行 `mvn spring-boot:run` 启动。
