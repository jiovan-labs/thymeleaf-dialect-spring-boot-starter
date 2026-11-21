[English](README.md) | [簡體中文](README.zh-CN.md) | [繁體中文](README.zh-TW.md)

# Thymeleaf 方言 Spring Boot Starter

讓 Spring Boot 應用快速整合 `thymeleaf` 方言，助力模板開發。

## 快速開始

- 匯入相依性
```xml
    <dependency>
        <groupId>com.jiovan.spring.starter</groupId>
        <artifactId>thymeleaf-dialect-spring-boot-starter</artifactId>
        <version>LATEST</version>
    </dependency>
```

> 預設情況下，此 starter 會自動生效，你可以透過 `jiovan.thymeleaf-dialect.enabled = false` 關閉它。

- 使用字首 `jiovan.thymeleaf-dialect` 設定 Spring Boot 的 `application.yml`（**可選**）
```yml
jiovan:
    thymeleaf-dialect:
        commons-lang-dialect:
            processor-order: 0
        commons-rng-dialect:
            processor-order: 0
```

- 此 starter 建立以下方言及其對應的構件：

| 方言類 | 對應構件 |
|------------------------------|---------------------------------------|
| CommonsLangExpressionDialect | org.apache.commons:commons-lang3 |
| CommonsRngExpressionDialect | org.apache.commons:commons-rng-simple |

- `CommonsLangExpressionDialect` 提供以下表示式及其對應的類：

| 表示式 | 對應類 |
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

- `CommonsRngExpressionDialect` 提供以下表示式及其對應的類：

| 表示式 | 對應類 |
|-----------------|------------------------------------------------|
| #randomProvider | org.apache.commons.rng.simple.RandomSource#JDK |

- 按如下方式編寫模板程式碼（以 `img` 為例）
```
<img th:src="@{${'/asset/img/foobar-' + #randomProvider.nextInt(1,3) + '.png'}}">
```
啊，看起來是不是很酷？

## 文件

- GitHub：https://github.com/jiovan-labs/thymeleaf-dialect-spring-boot-starter
- Thymeleaf GitHub：https://github.com/thymeleaf/thymeleaf
- Thymeleaf 主頁：https://thymeleaf.org

## 環境要求

- jdk 17+

## 許可證

本專案採用 [Apache License 2.0](https://www.apache.org/licenses/LICENSE-2.0) 許可證。

請參閱 `NOTICE.txt` 檔案瞭解所需的宣告與歸屬資訊。

## 捐贈

喜歡這個工具包嗎？歡迎[向我們捐贈](https://jiovan.com/donation)以支援開發。

## 版權

北京玖漫科技有限公司

## 網站

- 玖漫：https://jiovan.com
