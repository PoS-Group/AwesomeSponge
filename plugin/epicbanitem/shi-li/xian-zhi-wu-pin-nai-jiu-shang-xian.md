# 限制物品耐久上限

## 1. 创建规则，匹配所有损伤值小于100的物品

![/ebi c larger\_eg {&quot;Damage&quot;:{&quot;$lt&quot;:30}}](../../../.gitbook/assets/image%20%2815%29.png)

由[文档](https://docs.ebi.team/zh/rules-for-querying-and-updating?id=%e6%af%94%e8%be%83%e8%bf%90%e7%ae%97%e7%ac%a6)可知比较运算符，lt改为gt即可匹配损伤值大于100的物品（以此可限制一些物品的能量上限）

## 2. 更新规则，设置物品损伤值为100

![{&quot;$set&quot;:{&quot;Damage&quot;:100}}](../../../.gitbook/assets/image%20%2818%29.png)

![](../../../.gitbook/assets/image%20%289%29.png)

下附配置

```text
"larger_eg" {
    priority=5
    query {
        Damage {
            "$lt"=100
        }
        id="minecraft:diamond_sword"
    }
    trigger-default-setting=FALSE
    update {
        "$set" {
            Damage=100
        }
    }
    use-trigger {
        "epicbanitem:click"=true
        "epicbanitem:drop"=true
        "epicbanitem:join"=true
        "epicbanitem:pickup"=true
        "epicbanitem:use"=true
    }
    world-default-setting=UNDEFINED
}
```

