# Do Never Use Hardcode in I18n

"Hardcoding" means you embed something, especially texts here, into codes or otherwhere, where they are not changable through language file, resource packs or configuration.

I am a native Chinese speaker, and I have hosted or participated in translating a few mods into Chinese including *NuclearCraft: Overhauled* and it's dependents, *The Undergarden*, *Farmer's Delight*, *The Lord of the Rings* and else. In this progress, I noted many mods ignoring or rejecting internatiionalization, not care about speakers of other languages who know English not that well.

A good mod should consider about localizing, and use no hardcode. If you are not a chauvinist, and you ever want your mod get localized, receive language files and be spread over non-native speakers of English while gaining more downloads, you should make sure there is no problem in i18n.

I will show examples of not obeying internationalizing standards enough. Most examples are in 1.12.2, but that does not matter. All copyrights belongs to modders themselves, and I will delete them if with tort. There are endless examples, and these are just some drops in the ocean.

I. The Only Principle: **Do Not Hardcode ANYTHING**

1. Don't Hardcode Strings

All strings should be translatable. This includes all the item/block names ~~(no one would hardcode these, right?)~~, descriptions and tooltips, book/lore entries, GUI texts and all other strings.

Examples of hardcoding tooltip:

[*Sushi Go Crafting*](https://www.curseforge.com/minecraft/mc-mods/sushigocrafting)

[*Patchouli Guidebook*](https://www.curseforge.com/minecraft/mc-mods/patchouli)

Example of hardcoding book/lore entries:

[*The Lord of the Rings Legacy*](https://www.curseforge.com/minecraft/mc-mods/the-lord-of-the-rings-mod-legacy/) (not exactly hardcoding though, but no i18n)

Example of hardcoding GUI texts:

[*The One Probe*](https://www.curseforge.com/minecraft/mc-mods/the-one-probe)

**Solution:**

a. Use `setTranslationKey()`, `I18n.format()`/`I18n.translateToLocal()`, `TextComponentTranslation()` or any other methods defined by Minecraft or yourself.

b. Use ICU4J when processing ordinal numbers or other regular strings.

2. Don't Hardcode Texts **into** Pictures

It's not unacceptable to embed texts into pictures, but please at least make them localizable, like what *Patchouli Guidebook* does for images in books.

Example of hardcodig text into picture:

[*Arcane Archives*](https://www.curseforge.com/minecraft/mc-mods/arcane-archives)

**Solution:**

a. Put resources into a folder named with language code such as `en_us`, and invent a way to hot-reload pictures when switching in languages (recommended), like *Patchouli Guidebook*.

b. Invent a way to render formatted and localizable texts floating over the image.

3. Don't Hardcode Rules **Piecing Together Texts and Pluralizing Words**

Each language has its own rule transforming words. `Iron Sword` in Spanish is "Sword of iron" (`Espada de hierro`; it has different sequence and capitalization of words), and in Chinese is "ironsword" (`铁剑`; there is lack of capitalization and space). It is unacceptable to most people seeing `de hierro Espada` and `铁 剑` as they are ugly and grammatically wrong. So you can not use text rules like `I18n.format(key_name_iron) + " " + I18n.format(key_name_sword)`.

Solution **?**:

~~a~~. Add a key into all language files, such as `key.modid.text.rule=%1$s %2$s`, then use `String.format(I18n.translateToLocal("key.modid.text.rule"), I18n.translateToLocal(key_name_iron), I18n.translateToLocal(key_name_sword))`, so that Spanish localizers should be able to change the value to `%2$s %1$s` and so as `%s%s` for Chinese localizers. **BUT:**

`Chainmail Helmet` and `Iron Helmet` are both `Helmet`, but in German they are `Kettenhaube` and `Eisenhelm`, where `Helmet` turned into `haube` and `helm`, this is determined by their grammar genders: `haube` is feminine, and `helm` is masculine.

Solution **?**:

~~b~~. Add many keys which describe rule of piecing together strings for every tool, armor and so on, into all language files as described before, then call each of them. In this way, every type of item gets an independent rule piecing together texts, instead of sharing a common one. **BUT:**

This did not solve the problem of `Kettenhaube` and `Eisenhelm`. If you set a rule as `key.modid.text.rule.helmet` you will find there is no rule matches both word in German.

**Solution:**

a. From *LibVulpes*: Introduce a function to check if there is a specific kind of key existing. If true, use its value as the string to output, else you simply piece strings together and output:

```java
// Not completely true codes, only for demonstration

String translate = "tile." + MODID + "." + itemType + "." + material + ".name";
if (I18n.canTranslate(translate))
    return I18n.translateToLocal(translate);
return ("" + I18n.translateToLocal("material." + material + ".name") + " " + I18n.translateToLocal("type." + itemType + ".name")).trim();

// en_us.lang
type.gear.name=Gear
type.ore.name=Ore
material.Titanium.name=Titanium
material.Steel.name=Steel
// Output: Titanium Gear, etc.

// zh_cn.lang
tile.libvulpes.gear.Titanium=钛齿轮
tile.libvulpes.gear.Steel=钢齿轮
tile.libvulpes.ore.Titanium=钛矿石
tile.libvulpes.ore.Steel=钢矿石 (such string will never be called actually)
// Output: 钛齿轮, etc.
```

This way of solution solves the problem very well and is highly recommended. In English and some other language files the workspace is still as clean as before, and in all languages the output item name is grammatically and visually correct. But if there is a need of generating strings from configuration files, and you have to piece strings from many places together, you can check this:

b. From *NuclearCraft: Overhauled*: Introduce a key allowing localizer to customize the translating method in language file with `JS_ENGINE.eval()`. It is also easy for English itself to pluralize in this way, and it is highly recommended too.

```java
public static int getPluralRule(int count) throws ScriptException
{
    return (int) JS_ENGINE.eval(Lang.localise("nc.sf.plural_rule", count));
}

// en_us.lang
nc.sf.plural_rule=%d == 1 ? 0 : 1
nc.sf.reactor_casing0=%s reactor casing
nc.sf.reactor_casing1=%s reactor casing
nc.sf.conductor0=%s conductor
nc.sf.conductor1=%s conductors

// zh_cn.lang
nc.sf.plural_rule=0
nc.sf.reactor_casing0=%s反应堆外壳
nc.sf.conductor0=%s反应堆连接器
// There is no plural form of nouns in Chinese
```

This mod has other string formatter features, including logical process of `and`, `or` and `no`. It can deal with some forms of grammar genders also, as its customizable strings include both attributive and objective words.I believe you can learn much by reading [its code](https://github.com/tomdodd4598/NuclearCraft/blob/1.12.2o/src/main/java/nc/util/I18nHelper.java).

Are these all above **enough**?

Well, `سيف حديدي` is `Iron Sword` in South Africa Arabic, and it is written from right to left (RTL). With mixing this into a text, you do not know what is going to happen. I do not know either, though I know ICU4J has function to deal with this. Considering that there is currently not many localizations from RTL languages, this is not that important. What is notable, is that there will always be exceptions in i18n and l10n, so the only way with completely no problem is allow localizers to change the whole string instead piecing some strings together.

4. 字符处理机制
处理某类字符时，应当考虑到其他语言当中是否也会出现对应字符，如标点符号的全半角、空格等
E. g. Botania, Psi, Immersive Engineering, ToroQuest
字符处理机制比如 Botania 和 Psi 的旧版本，它们的手册作为 Patchouli 的雏形不太完善，再比如 Immersive Engineering：按空格分词，汉语文件里都需要手动每 12 个字加一个空格
解决方法：过正则加空格 https://github.com/CFPAOrg/Minecraft-Mod-Language-Package/pull/1559

https://www.curseforge.com/minecraft/mc-mods/thaumcraft-localization-optimizer

-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-

II. 可通过资源包更改
E. g. Reika

III. 不会有各种异常情况

1. 过长字符串导致溢出界面/强制设定背景宽度

2. 换行：别依赖空格（wrapfix）

3. 分辨率（是否为 Unicode 字体）

4. 编码：UTF + 8

5. 左右混排 rtl H/t

IV. 作者还可以帮助译者，更新时附上语言文件的更改（有现成轮子）

V. 在键里包含 ModID

https://github.com/mekanism/Mekanism/issues/4698

~~VI~~. So Many Enchantments 枚举了一万多个罗马数字到语言文件里，好在不是硬编码，但也没什么好的