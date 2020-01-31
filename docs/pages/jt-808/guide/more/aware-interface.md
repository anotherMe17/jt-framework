# Aware接口

首先声明这种 `Aware` 接口是从 `Spring` 中借鉴(抄袭)的 :joy::joy::joy::joy::joy::joy:。

所以你要是知道 `Spring` 中的诸如 `ApplicationContextAware`、`EnvironmentAware` 等就几乎没必要看本小节了。

## 为什么会提供？

在用注解解析映射请求报文到实体类的时候，字段长度等的计算可能会依赖于消息头中的一些属性。

所以在基于注解的实体类映射时，你可以给实体类实现这些接口以自动注入一些其他信息。

::: danger 注意
目前为止，这些Aware接口只能用于 `请求体消息实体类` 中。
:::

## RequestMsgHeaderAware

每次消息处理时为实体类注入 `RequestMsgHeader` 实例。

## RequestMsgMetadataAware

每次消息处理时为实体类注入 `RequestMsgMetadata` 实例。