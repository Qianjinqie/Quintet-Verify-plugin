# Quintet-Verify-plugin
> Quintet-Verify 认知增强插件包 —— 通过标准化挂载点扩展五角色行为，不侵入核心流程。

---

## 项目定位

`qv-extras` 是 [Quintet-Verify](https://github.com/Qianjinqie/Quintet-Verify) 的可选扩展包，提供一系列认知增强插件，通过主框架暴露的 `pre_act_hooks` / `post_act_hooks` 标准化挂载点注入行为。

插件**默认全部关闭**，由用户在 Web 控制台或配置中按需开启。核心框架不受插件影响，未安装本包时 Quintet-Verify 完整功能不受任何影响。


## 设计哲学

- **非侵入**：不修改 Quintet-Verify 核心代码，仅通过挂载点注入
- **按需启用**：所有插件默认关闭，用户根据任务需求选择性开启
- **可组合**：插件之间相互独立，可任意组合使用


## 快速开始

### 安装
直接从源码安装：

```bash
git clone https://github.com/Qianjinqie/Quintet-Verify-plugin.git
cd Quintet-Verify-plugin
pip install .
```

使用

安装后，插件会自动注册到 Quintet-Verify 的挂载点。在 Web 控制台中开启对应插件的 flags 开关即可启用，或在配置中设置：

```python
from quintet_verify import PublicState, QuintetState

state = QuintetState(
    public=PublicState(
        task="...",
        flags={
            "plugin_a": True,   # 开启插件 A
            "plugin_b": False,  # 关闭插件 B
            # ...
        }
    )
)
```

与主框架的关系

 Quintet-Verify（主框架） qv-extras（本包）
核心五角色制衡 ✅ 核心能力 ❌ 不涉及
三条铁律 ✅ 核心能力 ❌ 不涉及
认知增强插件 ❌ 不包含 ✅ 本包提供
依赖关系 独立运行，不依赖本包 依赖主框架（运行时检测挂载点）

本包是主框架的可选增强层，而非必要组件。

理论溯源与独立性声明

qv-extras 的部分机制设计（结论前桥接、广播枢纽、元认知控制即动作）受到 J-Space Cognition Suite V3.6（doi:10.5281/zenodo.21971181）的启发，借鉴了其关于“Dense Track”和认知标记（✓/?/✗）的理念。

但本仓库的所有代码均为独立实现，未复制或翻译 J-Space 的任何源代码、提示词模板或协议文案。根据 Apache License 2.0 对“衍生作品”的定义，本插件作为通过标准化接口调用的独立模块，不构成 J-Space 的衍生作品或分支。

我们对 J-Space 团队的原创工作表示敬意与感谢，并建议读者将其作为理解本插件设计背景的有益对照参考。

Quintet-Verify 主框架的完整理论溯源与独立性声明，请参阅主仓库 README。

许可证

本项目的许可证与主框架保持一致：Apache License 2.0。

详见 LICENSE 文件。

相关链接

· Quintet-Verify 主框架 — 多智能体认知控制框架
· J-Space Cognition Suite V3.6 — 单一模型认知管理（doi:10.5281/zenodo.21971181）
