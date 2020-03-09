---
description: 适用于植物魔法花、工业等等使用 NBT 储存方块/物品类型的封禁
---

# 特殊物品封禁

_这里以植物魔法花为例_

## 1. 首先手持物品执行命令（taiga 赛高！）

![/ebi q](../../../.gitbook/assets/image%20%2810%29.png)

## 2. 将鼠标放至 type 可知路径为 tag.type

![/ebi q {&quot;tag.type&quot;:&quot;tigerseye&quot;}](../../../.gitbook/assets/image%20%287%29.png)

## 3. 由此创建规则

![/ebi c botania.taiga {&quot;tag.type&quot;:&quot;tigerseye&quot;}](../../../.gitbook/assets/image%20%285%29.png)

![](../../../.gitbook/assets/image%20%2812%29.png)

## 4. 到这步物品已经封禁成功了，但是通过对已放置的虎之眼查询，发现方块规则不同。

![/ebi q -l {}](../../../.gitbook/assets/image%20%2817%29.png)

## 5. 这将导致交互、破坏规则无法生效，不需要这两个触发器则无需以下步骤，以下仅为示范所用，实际应用中交互时替换为空气可能导致 mod 不可预知的错误（植物魔法虽然报错，但是没什么太大影响，其他 mod 未必如此，请谨慎测试）

 

![/ebi c bontaia.taiga\_tile {&quot;tag.BlockEntityTag.subTileName&quot;:&quot;tigerseye&quot;,&quot;id&quot;:&quot;botania:specialflower&quot;}](../../../.gitbook/assets/image%20%2818%29.png)

## 6. 至此教程全部完成

