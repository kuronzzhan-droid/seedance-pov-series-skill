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

1. **流程八步**：剧情分析 → 选素材（能复用不重出）→ 场景图提示词 → **看图定方位** → 15秒提示词 → 自检 → 用户提交 → 存档回填
2. **空间锚定五法**：坐标系唯一／视线即镜头／动作因果链／一拍一动作＋终点姿势／物理反馈——动作逻辑稳定不漂移的答案
3. **连续性三件套**：`连载状态.md`（唯一事实源）＋`角色档案.md`（性格三层/体态信号库/语言阶段/OOC清单）＋素材登记表（C角色/S场景/P道具编号）
4. **角色语言阶段**：长线角色说话能力渐进解锁（无语言期→单词期→短句期→…），写台词禁止越级——语言解锁本身就是角色弧光
5. **声音层**：只给"角色听到后会有反应"的声音——声音是角色耳朵演戏的理由
6. **基调**：真实沉浸为主、幽默为辅；每集结尾一个温柔停顿

## 文件结构

```
SKILL.md                          # 技能主文件（流程八步）
references/
  style-rules.md                  # 空间锚定五法·声音层·基调·自检清单
  seedance-constraints.md         # 官方输入约束·@语法·禁忌·敏感词排查
  templates.md                    # 场景图/15秒I2V/本集存档/连载状态/角色档案 五套模板
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
