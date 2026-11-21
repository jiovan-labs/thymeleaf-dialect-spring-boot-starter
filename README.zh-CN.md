[English](README.md) | [简体中文](README.zh-CN.md) | [繁體中文](README.zh-TW.md)

# Thymeleaf 方言 Spring Boot Starter

让 Spring Boot 应用快速集成 `thymeleaf` 方言，助力模板开发。

## 快速开始

- 导入依赖
```xml
    <dependency>
        <groupId>com.jiovan.spring.starter</groupId>
        <artifactId>thymeleaf-dialect-spring-boot-starter</artifactId>
        <version>LATEST</version>
    </dependency>
```

> 默认情况下，此 starter 会自动生效，你可以通过 `jiovan.thymeleaf-dialect.enabled = false` 关闭它。

- 使用前缀 `jiovan.thymeleaf-dialect` 配置 Spring Boot 的 `application.yml`（**可选**）
```yml
jiovan:
    thymeleaf-dialect:
        commons-lang-dialect:
            processor-order: 0
        commons-rng-dialect:
            processor-order: 0
```

- 此 starter 创建以下方言及其对应的构件：

| 方言类 | 对应构件 |
|------------------------------|---------------------------------------|
| CommonsLangExpressionDialect | org.apache.commons:commons-lang3 |
| CommonsRngExpressionDialect | org.apache.commons:commons-rng-simple |

- `CommonsLangExpressionDialect` 提供以下表达式及其对应的类：

| 表达式 | 对应类 |
|--------------------|--------------------------------------------|
| #arrayUtils | org.apache.commons.lang3.ArrayUtils |
| #booleanUtils | org.apache.commons.lang3.BooleanUtils |
| #charUtils | org.apache.commons.lang3.CharUtils |
| #numberUtils | org.apache.commons.lang3.math.NumberUtils |
| #objectUtils | org.apache.commons.lang3.ObjectUtils |
| #randomStringUtils | org.apache.commons.lang3.RandomStringUtils |
| #regexUtils | org.apache.commons.lang3.RegExUtils |
| #stringUtils | org.apache.commons.lang3.StringUtils |
| #systemUtils | org.apache.commons.lang3.SystemUtils |

- `CommonsRngExpressionDialect` 提供以下表达式及其对应的类：

| 表达式 | 对应类 |
|-----------------|------------------------------------------------|
| #randomProvider | org.apache.commons.rng.simple.RandomSource#JDK |

- 按如下方式编写模板代码（以 `img` 为例）
```
<img th:src="@{${'/asset/img/foobar-' + #randomProvider.nextInt(1,3) + '.png'}}">
```
啊，看起来是不是很酷？

## 文档

- GitHub：https://github.com/jiovan-labs/thymeleaf-dialect-spring-boot-starter
- Thymeleaf GitHub：https://github.com/thymeleaf/thymeleaf
- Thymeleaf 主页：https://thymeleaf.org

## 环境要求

- jdk 17+

## 许可证

本项目采用 [Apache License 2.0](https://www.apache.org/licenses/LICENSE-2.0) 许可证。

请参阅 `NOTICE.txt` 文件了解所需的声明与归属信息。

## 捐赠

喜欢这个工具包吗？欢迎[向我们捐赠](https://jiovan.com/donation)以支持开发。

## 版权

北京玖漫科技有限公司

## 网站

- 玖漫：https://jiovan.com
