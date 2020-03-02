# \[WIP\] 拾取绑定

1. 通过 [Nucleus](../../nucleus/) 添加一条描述到任一物品

![/lore add &amp;7&#x6B64;&#x7269;&#x54C1;&#x62FE;&#x53D6;&#x540E;&#x7ED1;&#x5B9A;](../../../.gitbook/assets/image%20%281%29.png)

2. 查询当前标签内容

![/ebi q {}](../../../.gitbook/assets/image%20%283%29.png)

3. 通过点击相应标签获得正确路径与对应值，再次查询确认规则

![/ebi q {&quot;tag.display.Lore&quot;:&quot;\u00a77&#x6B64;&#x7269;&#x54C1;&#x62FE;&#x53D6;&#x540E;&#x7ED1;&#x5B9A;&quot;}](../../../.gitbook/assets/image%20%284%29.png)

4. 创建规则（no-capture 目的为不依赖于物品 ID，检测所有拥有此 Lore 的物品），因目的为拾取绑定，调整触发器为拾取时触发，一切调整建议在配置文件中直接更改

![/ebi create bound.pick --no-capture {&quot;tag.display.Lore&quot;:&quot;\u00a77&#x6B64;&#x7269;&#x54C1;&#x62FE;&#x53D6;&#x540E;&#x7ED1;&#x5B9A;&quot;}](../../../.gitbook/assets/image%20%285%29.png)

当拾取物品时，物品 Lore 变化，以便下一个规则的匹配

5. 

