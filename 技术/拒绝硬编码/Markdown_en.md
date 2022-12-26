# Never Use Hardcode in I18n

"Hardcoding" means to embed something, especially texts in this passage, into source code or otherwhere, where they are not changable through language file, resource packs, configuration or other files which are able to be easily customized by players or localizers.

I am a native Chinese speaker, and I have hosted or participated in translating a few mods into Chinese, including *NuclearCraft: Overhauled* and its addons, *Sushi Go Crafting*, *The Lord of the Rings* and others. In my translating experience, I noticed that many mods ignore, or even reject to internationalization. This greatly reduces gaming experience of non-English speakers who do not understand English well.

A good mod should care about localizing, and use no hardcode. If you are not a Chauvinist, you should consider about i18n. I18n makes players around the world able to share the same nice gaming experience, and it creates a more friendly environment of a mod.

I will show some examples of not obeying i18n standards enough. Most examples are in 1.12.2, but that does not matter. Some problems have been fixed, but others are not. All copyrights belongs to modders themselves, and I will delete them if there is tort. These examples are just some drops in the ocean, amd the solutions listed here are not the final answer either. There are endless problems on the way making i18n, and no individual can solve them independently.

## The Only Principle: Do Not Hardcode ANYTHING

### Do Not Hardcode Strings

All strings should be translatable. This includes all the item/block names ~~(no one is able to hardcode these becuase of *Forge*, right?)~~, descriptions and tooltips, book/lore entries, GUI texts and all other strings.

#### Examples of hardcoding tooltip

[*Sushi Go Crafting*](https://www.curseforge.com/minecraft/mc-mods/sushigocrafting)

![](images/sushi_ingredient.png)

[*Patchouli Guidebook*](https://www.curseforge.com/minecraft/mc-mods/patchouli) (hardcoding of ordinal numbers)

![](images/patchouli_ordinal_number.png)

#### Example of hardcoding book/lore entries

[*The Lord of the Rings Legacy*](https://www.curseforge.com/minecraft/mc-mods/the-lord-of-the-rings-mod-legacy/) (not exactly hardcoding though, but no i18n)

![](images/lotr_uncustomizable_text.png)

#### Example of hardcoding GUI texts

[*The One Probe*](https://www.curseforge.com/minecraft/mc-mods/the-one-probe)

![](images/top_untranslatable.png)

#### Solution

a. Use `setTranslationKey()`, `I18n.format()`~~/`I18n.translateToLocal()` (not after 1.12.2)~~, `TextComponentTranslation()` or any other method defined by Minecraft or yourself.

b. Use ICU4J to process ordinal numbers or other strings with regular transformation between languages. ICU4J is included in Minecraft.

### Do Not Hardcode Texts into Pictures

It's not unacceptable to embed texts into pictures, but you should at least make them localizable, like what *Patchouli Guidebook* does for images in books.

#### Example of hardcodig text into picture

[*Arcane Archives*](https://www.curseforge.com/minecraft/mc-mods/arcane-archives)

![](images/archives_image.png)

#### Solution

a. Put resources into a folder named with language code such as `en_us`, and invent a way to hot-reload pictures when switching to another language in game (recommended), like *Patchouli Guidebook*.

b. Invent a way to render formatted and localizable texts floating over the image.

### Do Not Hardcode Rules **Piecing Together Texts and Pluralizing Words**

Each language has its own rule transforming words. `Iron Sword` in Spanish is "Sword of iron" (`Espada de hierro`; it has different sequence and capitalization of words), and in Chinese is "ironsword" (`铁剑`; there is lack of capitalization and space). It is unacceptable to most people seeing `de hierro Espada` and `铁 剑` as they are ugly or grammatically wrong. So you cannot use text rules like `I18n.format(key_name_iron) + " " + I18n.format(key_name_sword)`.

#### Example of space which should not exist

[*LibVulpes*](https://www.curseforge.com/minecraft/mc-mods/libvulpes) (already fixed in 2017)

![](images/libvulpes_space.png)

#### Example of unchangable pluralization

[*ToroQuest Revamped*](https://cursefire.com/minecraft/mc-mods/toroquest-revamped)

![](images/toro_plural.png) (`绿宝石s` refers to "emerald**s**")

#### Solution *?*

~~a~~. Add a key into all language files, such as `key.modid.text.rule=%1$s %2$s`, then use `String.format(I18n.format("key.modid.text.rule"), I18n.format(key_name_iron), I18n.format(key_name_sword))`, so that Spanish localizers should be able to change the value to `%2$s %1$s` and so to Chinese localizers as `%s%s`. **BUT:**

In Spanish, `(Material) Horse Armor` is actually `Armadura (material) para caballo`. This creates a problem to localizers: if you add `para caballo` into `key.modid.text.rule`, name of every tool or armor will contain `para caballo`; and if you add `para caballo` into the keys for materials, it will come to the same result.

#### Solution *?*

~~a~~. Add many keys which describe rule of piecing together strings for every type of tool, armor and so on, into all language files as described before, then call each of them. In this way, every type of item gets an independent rule piecing together texts, instead of sharing a common one. **BUT:**

`Stone Pickaxe` and `Stone Axe` have the same attributive word in English: `Stone`. But in Czech, there are two different prefixes: `Kamenný` and `Kamenná`, respectively before `krumpáč` (pickaxe) and `sekera` (axe). Also, `Chainmail Helmet` and `Iron Helmet` are both `Helmet` in English, but in German they are `Kettenhaube` and `Eisenhelm`. This solution cannot solve the problem of Czech, German and other similar languages. If you set a rule as `key.modid.text.rule.helmet` you will find no rule there matches both words in German.

I do not understand why the same word `Helmet` turns into different words `haube` and `helm`, or why `Stone` turns into `Kamenný` and `Kamenná`. Maybe that is because of grammar genders, or because translators chose to make names more detailed, but this problem exists anyway, so it has to be dealed with.

#### Solution

a. From *LibVulpes*: Introduce a function to check if there is a specific kind of key existing. If true, use its value as the of item name, else you simply piece strings together and output:

```java
// Not completely true codes, only for demonstration

String translate = "tile." + MODID + "." + itemType + "." + material + ".name";
if (I18n.canTranslate(translate))
    return I18n.format(translate);
return ("" + I18n.format("material." + material + ".name") + " " + I18n.format("type." + itemType + ".name")).trim();

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
tile.libvulpes.ore.Steel=钢矿石 (not really)
// Output: 钛齿轮, etc.
```

This way of solution solves the problem very well and is highly recommended. In English and some other language files the workspace is still as clean as before, and in all languages the item name is grammatically and visually correct in game. But if there is a need of generating strings from configuration files, and you have to piece strings from many places together, you can check this:

b. From [*NuclearCraft: Overhauled*](https://www.curseforge.com/minecraft/mc-mods/nuclearcraft-overhauled): Introduce a key allowing localizer to customize the translating method in language file with `JS_ENGINE.eval()`. It is also easy for English itself to pluralize in this way, and it is highly recommended too.

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

This mod has other string formatter features, including logical process of `and`, `or` and `no`. It can deal with some forms of grammar genders also, as its customizable strings include both attributive and objective words. I believe you can learn much by reading [its code](https://github.com/tomdodd4598/NuclearCraft/blob/1.12.2o/src/main/java/nc/util/I18nHelper.java).

And are these all above **enough**? Well, `سيف حديدي` is `Iron Sword` in South Africa Arabic, and it is written from right to left (RTL). With mixing this into a text, you do not know what is going to happen. I do not know either, though I know ICU4J is designed to deal with this. Considering that there is currently not so many localizations from RTL languages, and even Minecraft didn't show RTL texts well, this problem is complex and not that important. What is notable, is that there will always be exceptions in i18n and l10n, so the only way with completely no problem, is to allow localizers to change the whole string instead piecing some strings together.

### Do Not Hardcode Text Process Mechanics

Most books in Minecraft mods split a long string into lines by a half-width space: `-> <-`. But in Chinese and Japanese, there is no such space completely. So when processing any specific character, you should consider about whether there is such charatcer, and whether it is used as you thought in other languages. You may not choose the quotation mark `'` as a grammar symbol, because it is widely used in French such as `d'avoir`, and it would not be a good choice to make your renderer depend on punctuation marks because they work in different ways in different languages and some language may not have them: double quote `"` does not exist in Russian, and all half-width marks (such as `.`) are full-width (such as `。`) in Chinese and Japanese (for difference between half-width and full-width, you can check [Wikipedia](https://en.wikipedia.org/wiki/Halfwidth_and_fullwidth_forms)). Ironically, Minecraft itself supports full-width marks badly until recent years, but that does not mean it is useless to consider about them: though supported not that good, they are still supported and exist in texts, and there are also third-party resource packs fixed full-width problems.

#### Examples not splitting Chinese texts correctly

[*Botania*](https://www.curseforge.com/minecraft/mc-mods/botania) (solved in later Minecraft versions with *Patchouli Guidebook*, but never in 1.12.2; the first line has no space in file, and the second one has in-game invisible space every 12 characters, which were added manually or with RegEx; those spaces make localization workspaces messy and unmaintainable)

![](images/botania_line_splitting.png)

[*Immersive Engineering*](https://www.curseforge.com/minecraft/mc-mods/immersive-engineering) (fixed; it splitted lines well, but with an overflowed amount of charcaters, it created a new line every time meeting a space; [something like this](https://github.com/BluSunrize/ImmersiveEngineering/commit/de5ccd69710603e857781be4a83a17b7d6e9d88b) caused crash in Japanese too)

![](images/immeng_line_splitting.png) (sorry for unclear image)

#### Example and solution of showing locked researches in [*Thaumcraft*](https://www.curseforge.com/minecraft/mc-mods/thaumcraft)

[*Thaumcraft Localization Optimizer*](https://www.curseforge.com/minecraft/mc-mods/thaumcraft-localization-optimizer)

#### Solution

a. Optimize your own renderer or use renderer by Minecraft.

b. Ask players to install [*WrapFix*](https://www.curseforge.com/minecraft/mc-mods/wrapfix) or such third-party mods.

# Some Other Suggestions and Problems on I18n

## Customizable via Resource Packs

#### Examples not changable via resource packs

[*ChromatiCraft*](https://www.curseforge.com/minecraft/mc-mods/chromaticraft) (working as intended)

[*The Lord of the Rings Legacy*](https://www.curseforge.com/minecraft/mc-mods/the-lord-of-the-rings-mod-legacy/)

## Ensure No Exceptions Happening

### Definition Ratio and GUI Scale Problem of Unicode Font

I guess this might happen when Unicode font is enabled, but I have not studied on this well.

#### Example of unclear characters

[*NuclearCraft Reactor Builder*](https://www.curseforge.com/minecraft/mc-mods/nuclearcraft-reactor-builder) (with Chinese charatcers in the normal resolution on my device; obviously it contains some hardcode strings too
)

![](images/ncrb_resolution.png)

#### Example of not considering Unicode font

[*The Lord of the Rings Legacy*](https://www.curseforge.com/minecraft/mc-mods/the-lord-of-the-rings-mod-legacy/)

![](images/lotr_unicode_font.png)

### Use UTF-8 without BOM Encoding

You can use `#PARSE_ESCAPES` in `.lang` files to get to [Java Properties](https://docs.oracle.com/javase/8/docs/api/java/util/Properties.html#load-java.io.Reader) features. If you do not use UTF-8 and call the default encoding of the client system, it might crash.

#### Example of not using UTF-8 and solution

[*Electroblob's Wizardry*](https://github.com/Electroblob77/Wizardry/pull/479)

## Add the ModID into Translation Keys

If you do not, your keys are likely to conflict with other mods, and override those or get overrided by those. Some even conflict with vanilla Minecraft. If you are sure that your key will never conflict (such as `item.no.one.would.use.this.key.i.am.pretty.sure.asdgdsafgasfd.name`), then you can leave it behind.

#### Example of mod of key conflict and solution

[*Mekanism*](https://github.com/mekanism/Mekanism/issues/4698)

## Why Do You Enum Thousands of Roman Numerals in Language File?

#### Example of enumming

[*So Many Enchantments*](https://www.curseforge.com/minecraft/mc-mods/so-many-enchantments)

```
// ......
enchantment.level.3994=MMMCMXCIV
enchantment.level.3995=MMMCMXCV
enchantment.level.3996=MMMCMXCVI
enchantment.level.3997=MMMCMXCVII
enchantment.level.3998=MMMCMXCVIII
enchantment.level.3999=MMMCMXCIX
enchantment.level.4000=4000
enchantment.level.4001=4001
enchantment.level.4002=4002
enchantment.level.4003=4003
// ......
```