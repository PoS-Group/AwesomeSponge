# 拾取绑定

## 1. 通过 [Nucleus](../../nucleus/) 添加一条描述到任一物品

![/lore add &amp;7&#x6B64;&#x7269;&#x54C1;&#x62FE;&#x53D6;&#x540E;&#x7ED1;&#x5B9A;](../../../.gitbook/assets/image%20%2810%29.png)

## 2. 查询当前标签内容

![/ebi q {}](../../../.gitbook/assets/image.png)

## 3. 通过点击相应标签获得正确路径与对应值，再次查询确认规则  

![](../../../.gitbook/assets/image%20%284%29.png)

## 4. 创建规则（no-capture 目的为不依赖于物品 ID，检测所有拥有此 Lore 的物品），因目的为拾取绑定，调整触发器为拾取时触发，一切调整建议在配置文件中直接更改。更新规则修改如下

![/ebi create bound.pick --no-capture {&quot;tag.display.Lore&quot;:&quot;\u00a77&#x6B64;&#x7269;&#x54C1;&#x62FE;&#x53D6;&#x540E;&#x7ED1;&#x5B9A;&quot;}](../../../.gitbook/assets/image%20%281%29.png)

当拾取物品时，物品 Lore 更新，以便下一个规则的匹配

## 5. 创建规则

![/ebi c bound.bounded --no-capture {&quot;tag.display.Lore&quot;:&quot;\u00a77&#x7269;&#x54C1;&#x5DF2;&#x7ED1;&#x5B9A;&quot;}](../../../.gitbook/assets/image%20%282%29.png)

目的为阻止已绑定物品被丢出/转移至其他库存，所以更新规则设为空

## 6. 至此完成物品的拾取绑定，下面留两个作业

### 1. 不强制匹配 Lore 颜色，只匹配文本

### 2. 装备后绑定

下附此次配置

```text
bounded {
    custom-message="{item_pre}已绑定！"
    priority=5
    query {
        "tag.display.Lore"="§7物品已绑定"
    }
    trigger-default-setting=FALSE
    use-trigger {
        "epicbanitem:throw"=true
        "epicbanitem:transfer"=true
    }
    world-default-setting=UNDEFINED
}
pick {
    custom-message="{item_pre}已绑定！"
    priority=5
    query {
        "tag.display.Lore"="§7此物品拾取后绑定"
    }
    trigger-default-setting=FALSE
    update {
        "$set" {
            "tag.display.Lore.$[]"="§7物品已绑定"
        }
    }
    use-trigger {
        "epicbanitem:pickup"=true
    }
    world-default-setting=UNDEFINED
}
```

