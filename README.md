# seedance-pov-series-skill

**第一人称连载短剧的 Seedance 2.0 提示词流水线 Skill**（Claude Code / Agent Skill 格式）

把一段第一人称剧情变成一条 720p/15s 的 Seedance 2.0 视频提示词，并解决连载创作最难的问题：**跨集连续性**——角色不穿帮、方位不漂移、台词不 OOC、伏笔不丢失。

来自一个实际连载项目（毛茸异世界 OC 短剧，单季 12+ 集）的一线经验沉淀。

## 和现有高分项目的差异

| 项目 | 解决的问题 | 本 skill 的差异 |
|---|---|---|
| [Emily2040/seedance-2.0](https://github.com/Emily2040/seedance-2.0) | 单条提示词的导演式写法 | 已吸收其 I2V 铁律/反空话；在其上叠加连载连续性层 |
| [dexhunter/seedance2-skill](https://github.com/dexhunter/seedance2-skill) | 官方约束与@语法的准确使用 | 已吸收其约束表/禁忌清单；补充 POV 专用镜头白名单 |
| [liangdabiao/Seedance2-Storyboard-Generator](https://github.com/liangdabiao/Seedance2-Storyboard-Generator) | 剧本→分镜的批量转换 | 已吸收其素材编号(C/S/P)/声音层/尾帧衔接思路 |
| [MemeCalculate/moyin-creator](https://github.com/MemeCalculate/moyin-creator) | 全自动工具链 | 本 skill 是人机协作流程：AI 管文本，人管出图与提交 |
| **本项目** | **第一人称·连载·固定角色的系列短剧** | 连载状态/角色档案/素材登记三件套＋空间锚定文风＋看图后定稿工作流 |

## 核心方法（详见 SKILL.md 与 references/）

1. **流程八步**：剧情分析 → 选素材（能复用不重出）→ 场景图提示词 → **看图定方位** → 15秒提示词 → Master Checklist自检 → 用户提交 → 存档回填
2. **空间锚定五法**：坐标系唯一／视线即镜头／动作因果链／一拍一动作＋终点姿势／物理反馈——动作逻辑稳定不漂移的答案
3. **连续性三件套**：`连载状态.md`（唯一事实源）＋`角色档案.md`（性格三层/体态信号库/语言阶段/角色语法/OOC清单）＋素材登记表（C角色/S场景/P道具编号）
4. **角色语言阶段**：长线角色说话能力渐进解锁，写台词禁止越级——语言解锁本身就是角色弧光
5. **进阶模块八件**（v1.2-v1.9）：台词去AI味（遮名测试/角色语法）｜起承转合×BGM（转点四型/音效优先）｜POV镜头语言27技（角色碰镜头=碰我）｜接触戏（三拍分解/吻的种族解剖学）｜表演细节（表情三档制/招牌动作）｜多角色调度（扇形站位/明喻清零）｜氛围与画质（双色温防黄滤镜）｜开场钩子（2秒三选一/一句话转述）
6. **v2.0**：SKILL.md路由表统领全部模块＋Master Checklist（20条合并自检）＋冷启动指南＋边界判定速查

## 文件结构

```
SKILL.md                          # 主文件：流程八步·路由表·冷启动·边界判定
references/
  style-rules.md                  # 空间锚定五法·POV存在感·拟人度·去机械味·声音层·基调
  seedance-constraints.md         # 官方输入约束·@语法·禁忌·词数口径·敏感词排查
  templates.md                    # 五套模板 + 定稿前Master Checklist（20条）
  dialogue-rules.md               # 台词去AI味：遮名测试·角色语法三要素·答非所问
  structure-music.md              # 起承转合五拍映射·转点四型·BGM三通道
  pov-camera.md                   # POV镜头语言27技巧·稳定性分级
  contact-scenes.md               # 接触戏：公主抱/拥抱/亲吻（含种族解剖学）/击掌
  performance-details.md          # 毛发肌肉微变化·光影放大器·表情三档·招牌动作
  multi-character.md              # 多角色扇形调度·明喻清零·解释镜头消除·场景图两模式
  atmosphere-quality.md           # 风水雨雪氛围写法·双色温防黄滤镜·画质串v2
  hook-retention.md               # 0-2秒钩子·5秒微转·一句话转述·排播节奏
examples/
  demo-episode.md                 # 完整示例《雷雨夜岗哨》（带写法批注）
```

## 安装

Claude Code 个人技能目录：

```bash
git clone https://github.com/kuronzzhan-droid/seedance-pov-series-skill ~/.claude/skills/seedance-pov-series
```

或复制整个文件夹到项目 `.claude/skills/` 下。对话中给出一段第一人称剧情、或说"做一集"即可触发。

## 致谢

方法论部分整理并致谢以下开源项目与文档：
[Emily2040/seedance-2.0](https://github.com/Emily2040/seedance-2.0)（MIT）、
[dexhunter/seedance2-skill](https://github.com/dexhunter/seedance2-skill)、
[liangdabiao/Seedance2-Storyboard-Generator](https://github.com/liangdabiao/Seedance2-Storyboard-Generator)、
[MemeCalculate/moyin-creator](https://github.com/MemeCalculate/moyin-creator)，
以及字节跳动 Seedance 2.0 官方用户手册。

## License

MIT
