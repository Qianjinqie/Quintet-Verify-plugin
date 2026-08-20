# Quintet-Verify-plugin

Quintet-Verify Cognitive Enhancement Plugin Pack – extends the five‑role behaviour through standardised mount points without intruding into the core workflow.

## Table of Contents

- [Project Positioning](#project-positioning)
- [Design Philosophy](#design-philosophy)
- [Quick Start](#quick-start)
  - [Installation](#installation)
  - [Usage](#usage)
- [Relationship with the Main Framework](#relationship-with-the-main-framework)
- [Theoretical Origins and Independence Statement](#theoretical-origins-and-independence-statement)
- [License](#license)
- [Related Links](#related-links)

---

<a id="project-positioning"></a>
## Project Positioning

qv-extras is an optional extension package for Quintet-Verify. It provides a set of cognitive‑enhancement plugins that are injected via the standardised pre_act_hooks / post_act_hooks mount points exposed by the main framework.

All plugins are off by default – users enable them on demand via the Web console or configuration. The core framework is unaffected by plugins; without this package, Quintet-Verify’s full functionality remains intact.

---

<a id="design-philosophy"></a>
## Design Philosophy

- Non‑invasive – does not modify Quintet-Verify core code; injects only through mount points.  
- On‑demand enabling – all plugins are off by default; users selectively turn them on based on task requirements.  
- Composable – plugins are independent of each other and can be used in any combination.

---

<a id="quick-start"></a>
## Quick Start

<a id="installation"></a>
### Installation

Install directly from source:

```bash
git clone https://github.com/Qianjinqie/Quintet-Verify-plugin.git
cd Quintet-Verify-plugin
pip install .
```

<a id="usage"></a>

Usage

After installation, the plugins are automatically registered with Quintet-Verify’s mount points. Enable the corresponding plugin flags in the Web console, or set them in the configuration:

```python
from quintet_verify import PublicState, QuintetState

state = QuintetState(
    public=PublicState(
        task="...",
        flags={
            "plugin_a": True,   # enable plugin A
            "plugin_b": False,  # disable plugin B
            # ...
        }
    )
)
```

---

<a id="relationship-with-the-main-framework"></a>

## Relationship with the Main Framework

 Quintet-Verify (core) qv-extras (this package)
Core five‑role checks & balances ✅ core capability ❌ not involved
Three iron rules ✅ core capability ❌ not involved
Cognitive‑enhancement plugins ❌ not included ✅ provided by this package
Dependency Runs independently, does not depend on this package Depends on the main framework (detects mount points at runtime)

This package is an optional enhancement layer for the main framework, not a required component.

---

<a id="theoretical-origins-and-independence-statement"></a>

## Theoretical Origins and Independence Statement

Some mechanism designs in qv-extras (pre‑conclusion bridging, broadcast hub, metacognitive control as action) are inspired by J‑Space Cognition Suite V3.6 (doi:10.5281/zenodo.21971181), drawing on its concepts of “Dense Track” and cognitive markers (✓/?/✗).

However, all code in this repository is independently implemented; no source code, prompt templates, or protocol texts from J‑Space have been copied or translated. Under the definition of “derivative work” in the Apache License 2.0, this plugin package – as an independent module invoked through standardised interfaces – does not constitute a derivative work or fork of J‑Space.

We express our respect and gratitude to the J‑Space team for their original work, and recommend readers refer to it as a useful comparative reference for understanding the design background of this plugin.

For the full theoretical origins and independence statement of the Quintet-Verify main framework, please see the main repository README.

---

<a id="license"></a>

## License

This project adopts the same license as the main framework: Apache License 2.0.

See the LICENSE file for details.

---

<a id="related-links"></a>

## Related Links

· Quintet-Verify main framework – Multi‑agent cognitive control framework
· J‑Space Cognition Suite V3.6 – Single‑model cognitive management