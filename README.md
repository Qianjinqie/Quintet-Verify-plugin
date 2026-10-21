[English](docs/README.en.md) | **简体中文** | [日本語](docs/README.ja.md) | [한국어](docs/README.ko.md) | [Español](docs/README.es.md) | [Français](docs/README.fr.md) | [Deutsch](docs/README.de.md) | [Português (BR)](docs/README.pt-BR.md) | [Русский](docs/README.ru.md)

# Quintet-Verify-plugin

Quintet-Verify 认知增强插件包 – 通过标准化挂载点扩展五角色行为，而不侵入核心工作流。

## 目录

- [项目定位](#project-positioning)
- [设计理念](#design-philosophy)
- [快速开始](#quick-start)
  - [安装](#installation)
  - [使用](#usage)
- [与主框架的关系](#relationship-with-the-main-framework)
- [理论渊源与独立性声明](#theoretical-origins-and-independence-statement)
- [许可证](#license)
- [相关链接](#related-links)

---

<a id="project-positioning"></a>
## 项目定位

qv-extras 是 Quintet-Verify 的可选扩展包。它提供一组认知增强插件，通过主框架暴露的标准化 pre_act_hooks / post_act_hooks 挂载点注入。

所有插件默认关闭 – 用户可通过 Web 控制台或配置按需启用。核心框架不受插件影响；没有本扩展包，Quintet-Verify 的完整功能依然完好。

---

<a id="design-philosophy"></a>
## 设计理念

- 非侵入 – 不修改 Quintet-Verify 核心代码；仅通过挂载点注入。  
- 按需启用 – 所有插件默认关闭；用户根据任务需求有选择地开启。  
- 可组合 – 插件彼此独立，可任意组合使用。

---

<a id="quick-start"></a>
## 快速开始

<a id="installation"></a>
### 安装

直接从源码安装：

```bash
git clone https://github.com/Qianjinqie/Quintet-Verify-plugin.git
cd Quintet-Verify-plugin
pip install .
```

<a id="usage"></a>

### 使用

安装完成后，插件会自动注册到 Quintet-Verify 的挂载点。在 Web 控制台中启用相应的插件标志，或在配置中进行设置：

```python
from quintet_verify import PublicState, QuintetState

state = QuintetState(
    public=PublicState(
        task="...",
        flags={
            "plugin_a": True,   # 启用插件 A
            "plugin_b": False,  # 禁用插件 B
            # ...
        }
    )
)
```

---

<a id="relationship-with-the-main-framework"></a>

## 与主框架的关系

 Quintet-Verify（核心） qv-extras（本扩展包）
核心五角色制衡 ✅ 核心能力 ❌ 不涉及
三条铁律 ✅ 核心能力 ❌ 不涉及
认知增强插件 ❌ 不包含 ✅ 由本扩展包提供
依赖关系 独立运行，不依赖本扩展包 依赖主框架（在运行时检测挂载点）

本扩展包是主框架的可选增强层，而非必需组件。

---

<a id="theoretical-origins-and-independence-statement"></a>

## 理论渊源与独立性声明

qv-extras 中的部分机制设计（结论前桥接、广播枢纽、作为行动的元认知控制）受 J‑Space Cognition Suite V3.6（doi:10.5281/zenodo.21971181）启发，借鉴了其“Dense Track”与认知标记（✓/?/✗）概念。

但是，本仓库中的所有代码均为独立实现；未复制或翻译任何来自 J‑Space 的源代码、提示词模板或协议文本。依据 Apache License 2.0 中对“衍生作品”的定义，本插件包作为通过标准化接口调用的独立模块，不构成 J‑Space 的衍生作品或 fork。

我们向 J‑Space 团队的原创工作致以敬意与感谢，并建议读者将其作为理解本插件设计背景的有益对比参考。

关于 Quintet-Verify 主框架的完整理论渊源与独立性声明，请参阅主仓库的 README。

---

<a id="license"></a>

## 许可证

本项目采用与主框架相同的许可证：Apache License 2.0。

详情请参阅 LICENSE 文件。

---

<a id="related-links"></a>

## 相关链接

· Quintet-Verify 主框架 – 多智能体认知控制框架
· J‑Space Cognition Suite V3.6 – 单模型认知管理

**注：其他语言版本如有翻译错误，请以本版本（简体中文）为准**
