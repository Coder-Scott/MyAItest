# MyAItest

Java Spring Boot 后端应用，用于 AI 相关功能测试与开发。

## 技术栈

- **JDK**: 17+ (当前使用 JDK 25)
- **Spring Boot**: 3.2.3
- **Maven**: 3.9.x
- **构建工具**: Maven Wrapper (mvnw)

## 快速开始

### 环境要求

- Java 17 或更高版本
- Maven 3.9+（或使用项目自带的 Maven Wrapper）

### 本地运行

```bash
# 使用 Maven Wrapper（无需全局安装 Maven）
./mvnw clean spring-boot:run      # Linux / macOS
mvnw.cmd clean spring-boot:run    # Windows

# 或使用系统 Maven
mvn clean spring-boot:run
```

启动后访问：http://localhost:8080

### 打包部署

```bash
mvn clean package -DskipTests
java -jar target/MyAItest-0.0.1-SNAPSHOT.jar
```

## API 接口

| 方法   | 路径                | 参数          | 说明         |
| ------ | ------------------- | ------------- | ------------ |
| GET    | `/api/hello`        | `name` (可选) | 返回问候消息 |
| GET    | `/api/health`       | -             | 健康检查     |

### 示例

```bash
# 问候接口
curl http://localhost:8080/api/hello?name=MyAItest
# {"message":"Hello, MyAItest!","time":"2026-05-04T14:31:00.123"}

# 健康检查
curl http://localhost:8080/api/health
# {"status":"UP","timestamp":"2026-05-04T14:31:00.123"}
```

## 项目结构

```
MyAItest/
├── pom.xml                                    # Maven 构建配置
├── .mvn/wrapper/                              # Maven Wrapper
│   ├── maven-wrapper.jar
│   └── maven-wrapper.properties
├── mvnw.cmd                                   # Windows Maven Wrapper 脚本
└── src/
    ├── main/java/com/myaitest/
    │   ├── MyAiTestApplication.java           # Spring Boot 启动类
    │   └── controller/
    │       └── HelloController.java           # API 控制器
    ├── main/resources/
    │   └── application.properties             # 应用配置
    └── test/java/com/myaitest/
        └── MyAiTestApplicationTests.java      # 单元测试
```

## 测试

```bash
mvn test
```

当前包含基础上下文加载测试，验证 Spring Boot 应用正常启动。

## License

MIT
