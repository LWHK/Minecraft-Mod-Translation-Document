# 拒绝国际化硬编码（草稿）

根本原因：为其他语言及修改文本考虑

I. 唯一原则：不要硬编码任何东西

1. 不要硬编码文字
E. g. Sushi Go Crafting, Patchouli Guidebook, 一个编码了上万条罗马数字的模组
解决方案：使用 Minecraft 内置的 I18n 类、使用 ICU4J、自动罗马数字生成

2. 不要硬编码文字到图像里
E. g. Arcane Archives
解决方案：造轮子添加字体渲染功能，或造轮子支持更改语言时热重载所显示的图像

3. 不要硬编码文本拼合规则
E. g. Tetra
物品名 = 材料名 + " " + 工具名
解决方案：
1) LibVulpes
if (canTranslate(总字符串的键)) 采用总字符串的键值;
else 采用拼合规则下的键值;
可以应对一切
2) NuclearCraft: Overhauled
nc.sf.字符拼合规则=%2$s %1$s
（附加提示：bool 处理复数：nc.sf.plural_rule=%d > 1 ? 1 : 0）
难以应对阴阳，只能应对语序
3) ICU4J?
```
对此我只能给出两种解决方案：
1. 类似于也有过这问题的 Advanced Rocketry 的，它提供一个函数 ifTranslatable() 检测一种符合特定语法的键是否存在，这种键的值是一个物品的完整名称（不经拼合），如果存在就采用它，否则按硬编码拼合
  这个方法也是个人认为的最优解
2. 枚举每个词的变形方式，取决于语言是否有复数形式、是否有阴阳性、是否有各种时态，总之就是越粘着越需要枚举，比如 NuclearCraft: Overhauled 当中为了满足代码化自定义摆放规则设置了这套系统（只包含是否有复数）
  这种方法我觉得很扯淡，如果是梵语，那就等着枚举几万种吧
3. 采用我没学过的 ICU4J
  游戏国际化实在是门学问。。这方面我就不了解了，请多指教
```

4. 不要硬编码字符处理机制
处理某类字符时，应当考虑到其他语言当中是否也会出现对应字符，如标点符号的全半角、空格等
E. g. Botania, Psi, Immersive Engineering
字符处理机制比如 Botania 和 Psi 的旧版本，它们的手册作为 Patchouli 的雏形不太完善，再比如 Immersive Engineering：按空格分词，汉语文件里都需要手动每 12 个字加一个空格
解决方法：过正则加空格 https://github.com/CFPAOrg/Minecraft-Mod-Language-Package/pull/1559

II. 可通过资源包更改
E. g. Reika

III. 不会有各种异常情况
1. 过长字符串导致溢出界面/强制设定背景宽度
2. 换行：别依赖空格（wrapfix）
3. 分辨率（是否为 Unicode 字体）
4. 编码：UTF + 8

IV. 作者还可以帮助译者，更新时附上语言文件的更改（有现成轮子）

~~V~~. 有模组编了一万多个罗马数字到代码里
