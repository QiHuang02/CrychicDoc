---
description: Single block machine settings
state: preliminary
progress: 100
backPath: ./Catalogue
---

# 基本设置 {#BasicOptions}

这个模块可以配置机器的[工作状态](#WorkingState)，其`基础配置`允许玩家设置该机器的`方块属性`、`物品属性`与`机器设置`

![basic option root](/imgs/mods/custom/mbd2/zh/basic-option-root.png)

## 方块属性 {#BlockProperties}

:::outlined
该处配置机器的[`方块属性`](https://minecraft.fandom.com/zh/wiki/%E6%96%B9%E5%9D%97%E7%8A%B6%E6%80%81)，游戏内部对每个属性都有着详细的提示，可通过将==鼠标移至问号框处获取==，因此只将它们列在此处并进行必要的拓展。
:::

:::details 详细一览
| 属性名 | 描述 | 选项 | 说明 | 重载类型 |
|--------|------|------|------|------|
| `渲染类型` | 方块的渲染类型 | `SOLID 实心渲染`: 完全不透明渲染，适用于**不需要任何透明效果**的方块，如石头和泥土。<br>`CUTOUT 镂空渲染`: 使用无mipmapping的alpha测试，**适用于需要通过Alpha通道实现透明效果**的方块，如树叶和铁栅栏。<br>`CUTOUT_MIPPED 镂空渲染（带Mip贴图）`: 启用 mipmapping的alpha测试，适用于**需要在远距离保持良好纹理表现的透明方块**。<br>`TRANSLUCENT 半透明渲染`: 使用alpha混合实现部分透明，适用于**需要部分透明效果的方块**，如玻璃和冰块。 | 控制方块的渲染方法 | 需要重启 |
| `使用AO渲染 (Use AO)` | 是否开启环境光遮蔽渲染 |`boolean`| 开启后可增加方块阴影的细节,提高视觉效果 | 需要重启 |
| `方块朝向 (Rotation State)` | 方块允许的旋转方向 | `ALL`: 所有方向<br>`NONE`: 无法旋转<br>`NONE_Y_AXIS`: X、Z 轴方向<br>`Y_AXIS`: 仅 Y 轴方向 | 控制方块在游戏中的放置方向 | 需要重启 |
| `方块碰撞箱 (Has Collision)` | 是否启用碰撞检测 |`boolean`| 开启后玩家和其他实体将无法穿过该方块 | 需要重启 |
| `动态形状 (Dynamic Shape)` | 是否启用动态形状 |`boolean`| 允许动态地设置该方块的形状 | 需要重启 |
| `能被岩浆点燃 (Ignited by lava)` | 方块是否可被岩浆点燃 |`boolean`| 影响方块与岩浆的交互 | 需要重启 |
| `可被忽略 (Is Air)` | 方块是否被视为空气 |`boolean`| 如果为 true,该方块将不会阻挡移动或放置 | 需要重启 |
| `是否导致窒息 (Is Suffocating)` | 方块是否会导致实体窒息 |`boolean`| 如果为 false,实体可以在方块内呼吸 | 需要重启 |
| `自发光 (Emissive)` | 方块是否会发光 |`boolean`| 开启后方块(的纹理）会在黑暗中发光 | 需要重启 | 
| `摩擦力 (Friction)` | 方块表面的摩擦系数 | `float` [0.0, +∞] | 0.0 = 无摩擦力 (极滑)<br>1.0 = 最大摩擦力 (极粗糙) | 需要重启 |
| `速度系数 (Speed Factor)` | 影响在方块上的移动速度 | `float` [0.0, +∞) | 1.0 = 正常速度<br>>1.0 = 加速 (如: 1.5 = 50%加速)<br><1.0 = 减速 (如: 0.5 = 50%减速) | 需要重启 |
| `跳跃系数 (Jump Factor)` | 影响从方块上起跳的高度 | `float` [0.0, +∞) | 1.0 = 正常跳跃<br>>1.0 = 增加跳跃高度<br><1.0 = 降低跳跃高度 | 需要重启 |
| `摧毁时间 (Destroy Time)` | 破坏方块所需的时间 | `float` [0.0, +∞) 秒 | 0.0 = 立即破坏<br>越高 = 越难破坏 | 需要重启 |
| `爆炸抗性 (Explosion Resistance)` | 方块抵抗爆炸的能力 | `float` [0.0, +∞) | 0.0 = 无抗性<br>越高 = 越能抵抗爆炸 | 需要重启 |
| `声音 (Sound)` | 与方块交互时播放的声音 | `SoundEvent` | 指定方块被破坏时的音效 | 需要重启 |
| `透明方块 (Transparent Block)` | 方块是否类似玻璃 |`boolean`| 如果为 true,方块将变为透明 | 不需要重启 |
:::

## 物品属性 {#ItemProperties}

:::outlined
该处配置机器作为物品存在时的属性，游戏内部对每个属性都有着详细的提示，可通过将==鼠标移至问号框处获取==，因此只将它们列在此处并进行必要的拓展。
:::

:::details 详细一览
| 属性名 | 描述 | 选项 | 说明 | 重载类型 |
|--------|------|------|------|------|
| `方块光照 (Use Block Light)` | 控制方块作为物品在GUI内的光照逻辑 |`boolean`| `true`：物品将以方块形式在侧边被照亮<br>`false`：物品将以物品形式在正面被照亮 | 不需要重启 |
| `GUI 3D显示 (Use GUI 3D)` | 控制方块作为物品时的渲染 |`boolean`| 控制物品在GUI内是否作为3D模型显示 | 不需要重启 |
| `物品渲染 (Item Render)` | 选择是否自定义物品的渲染 |`boolean`| `true`：单独为该方块选择一个渲染<br>`false`：使用机器的父状态作为默认渲染 | 不需要重启 |
| `最大堆叠数量 (Max Stack Size)` | 设置物品的最大堆叠数量 |`int` [1,64]| 物品的最大堆叠数量 | 需要重启 |
| `稀有度 (Rarity)` | 设置物品稀有度 |`Rarity`| 物品的稀有度 | 需要重启 |
| `物品提示 (Tooltip)` | 设置物品提示 |List<`Tooltip`>| 用来设置物品提示，也叫Lore。 | 不需要重启 |
| `槽位预览 (Slot Preview)` | 用于预览物品栏 |`none`| 仅用于预览 | none |
:::

## 机器设置 {#MachineSettings}

:::outlined
该处配置机器的`机器设置`，允许玩家设置该机器的属性与配方，可通过将==鼠标移至问号框处获取==，因此只将它们列在此处并进行必要的拓展。

该配置无需重启游戏。
:::

:::details 详细一览
| 属性名 | 描述 | 选项 | 说明 |
|--------|------|------|------|
| `机器等级 (Machine Level)` | 设置机器的等级 |`int` [0, +∞)| 设置机器的等级，可用于配方条件。 |
| `有UI (Has GUI)` | 是否显示GUI |`boolean`| 如果为 true,机器将显示GUI |
| `有配方逻辑 (Has Recipe Logic)` | 是否启用配方逻辑 |`boolean`| `false`：机器将不会处理配方。如果机器不需要处理配方，请设置为false来优化性能。 |
| `配方衰减值 (Recipe Damping Value)` | 设置配方衰减值 |`int` [0.0, +∞) | 如果配方处理正在等待，衰减值是当前进度减少的tick数。 |
| `配方类型 (Recipe Type)` | 设置机器的配方类型 |`RecipeType`| 设置机器对应的配方。 |
| `配方修改器 (Recipe Modifiers)` | 添加与修改配方的修改器 |List<`RecipeModifier`>| 用于实时修改 `自身/控制器` 配方，可以用它来制作 `升级/插件` 部件|

- 内容修改器：用于配方内容的内容修改器。例如物品数量、流体数量等。

|  |  |  |  |
|--------|------|------|------|
| `乘数 (Multiplier)` | 设置修改器乘数 |`float` [0.0, +∞)| 配方内容数量的乘数 |
| `加数 (Addition)` | 设置修改器加数 |`float` [0.0, +∞)| 配方内容数量的加数 |
| `目标内容 (Target Content)` | 修改工作方式 |`option`| `in`： 输入内容<br>`out`： 输出内容<br>`both`： 输入与输出内容 |

- 持续时间修改器：用于配方持续时间的修改器。

|  |  |  |  |
|--------|------|------|------|
| `乘数 (Multiplier)` | 设置修改器乘数 |`float` [0.0, +∞)| 配方持续时间的乘数 |
| `加数 (Addition)` | 设置修改器加数 |`float` [0.0, +∞)| 配方持续时间的加数 |

- 最大并行数：此值是机器在同一时间可以处理的最大配方数量，不要设置得太高。

|  |  |  |  |
|--------|------|------|------|
| `乘数 (Multiplier)` | 设置修改器乘数 |`float` [0.0, +∞)| 最大并行数的乘数 |
| `加数 (Addition)` | 设置修改器加数 |`float` [0.0, +∞)| 最大并行数的加数 |

|  |  |  |  |
|--------|------|------|------|
| `多方块部件设置 (MultiBlock Part Settings)` | 设置多方块部件 |`boolean`| `false`：机器将不会作为普通单方块运行。 `true`：机器将在单方块上支持作为多方块部件运行。 |
:::

## 多方块部件设置 {#FormedMachineSettings}

:::outlined
该处配置机器的`多方块部件设置`，允许玩家设置机器的`多方块部件`。
:::

::::details 详细一览
| 属性名 | 描述 | 选项 | 说明 |
|--------|------|------|------|
| `可共享 (Can Share)` | 是否可共享 |`boolean`| 该部件是否可以在多个多方块机器中共享 |
| `配方修改器 (Recipe Modifiers)` | 添加与修改配方的修改器 |List<`RecipeModifier`>| 用于实时修改 `自身/控制器` 配方，可以用它来制作 `升级/插件` 部件|

- **内容修改器**：用于配方内容的内容修改器。例如物品数量、流体数量等。

|  |  |  |  |
|--------|------|------|------|
| `乘数 (Multiplier)` | 设置修改器乘数 |`float` [0.0, +∞)| 配方内容数量的乘数 |
| `加数 (Addition)` | 设置修改器加数 |`float` [0.0, +∞)| 配方内容数量的加数 |
| `目标内容 (Target Content)` | 修改工作方式 |`option`| `in`： 输入内容<br>`out`： 输出内容<br>`both`： 输入与输出内容 |

- **持续时间修改器**：用于配方持续时间的修改器。

|  |  |  |  |
|--------|------|------|------|
| `乘数 (Multiplier)` | 设置修改器乘数 |`float` [0.0, +∞)| 配方持续时间的乘数 |
| `加数 (Addition)` | 设置修改器加数 |`float` [0.0, +∞)| 配方持续时间的加数 |

- **最大并行数**：此值是机器在同一时间可以处理的最大配方数量，不要设置得太高。

|  |  |  |  |
|--------|------|------|------|
| `乘数 (Multiplier)` | 设置修改器乘数 |`float` [0.0, +∞)| 最大并行数的乘数 |
| `加数 (Addition)` | 设置修改器加数 |`float` [0.0, +∞)| 最大并行数的加数 |

|  |  |  |  |
|--------|------|------|------|
| `代理控制器特性能力 (Proxy Controller Capabilities)` | 设置代理控制器特性 |`boolean`| 如果部件不包含所需的能力，部件将代理来自控制器特性的能力。 |

- **特性过滤器**

|  |  |  |  |
|--------|------|------|------|
| `特性名称过滤器 (Trait Name Filter)` | 设置特性名称过滤器 |`string`| 设置特性名称过滤器，只有名称匹配的特性才会被代理。 |
| `能力输入输出 (Capability IO)` | 机器所有面的能力行为 |`boolean`| `BOTH`： 代理内部与外部能力<br>`NONE`： 不代理任何能力<br>`IN`： 仅代理输入能力<br>`OUT`： 仅代理输出能力 |

::: info
方向有`内部 (Internal)`、`正面 (Front)`、`背面 (Back)`、`左侧 (Left)`、`右侧 (Right)`、`顶部 (Top)`、`底部 (Bottom)`。
:::

::: warning
如果你将顶部设置为 `OUT-输出`用于`物品能力特性`。机器顶部将只能被提取。
:::

::::