[English](README.en.md) | [简体中文](README.md) | [日本語](README.ja.md) | **한국어** | [Español](README.es.md) | [Français](README.fr.md) | [Deutsch](README.de.md) | [Português (BR)](README.pt-BR.md) | [Русский](README.ru.md)

# Quintet-Verify-plugin

Quintet-Verify 인지 강화 플러그인 팩 – 표준화된 마운트 포인트를 통해 핵심 워크플로우에 침입하지 않고 5역할 동작을 확장합니다.

## 목차

- [프로젝트 포지셔닝](#project-positioning)
- [설계 철학](#design-philosophy)
- [빠른 시작](#quick-start)
  - [설치](#installation)
  - [사용법](#usage)
- [메인 프레임워크와의 관계](#relationship-with-the-main-framework)
- [이론적 기원과 독립성 선언](#theoretical-origins-and-independence-statement)
- [라이선스](#license)
- [관련 링크](#related-links)

---

<a id="project-positioning"></a>
## 프로젝트 포지셔닝

qv-extras는 Quintet-Verify의 선택적 확장 패키지입니다. 메인 프레임워크가 노출하는 표준화된 pre_act_hooks / post_act_hooks 마운트 포인트를 통해 주입되는 인지 강화 플러그인 모음을 제공합니다.

모든 플러그인은 기본적으로 꺼져 있으며 – 사용자는 웹 콘솔이나 설정을 통해 필요에 따라 활성화합니다. 핵심 프레임워크는 플러그인의 영향을 받지 않고, 이 패키지가 없어도 Quintet-Verify의 전체 기능은 그대로 유지됩니다.

---

<a id="design-philosophy"></a>
## 설계 철학

- 비침입적 – Quintet-Verify 핵심 코드를 수정하지 않고, 마운트 포인트를 통해서만 주입합니다.  
- 온디맨드 활성화 – 모든 플러그인은 기본적으로 꺼져 있으며, 사용자가 작업 요구 사항에 따라 선택적으로 켭니다.  
- 조합 가능 – 플러그인은 서로 독립적이며 어떤 조합으로도 사용할 수 있습니다.

---

<a id="quick-start"></a>
## 빠른 시작

<a id="installation"></a>
### 설치

소스에서 직접 설치:

```bash
git clone https://github.com/Qianjinqie/Quintet-Verify-plugin.git
cd Quintet-Verify-plugin
pip install .
```

<a id="usage"></a>

### 사용법

설치 후 플러그인은 Quintet-Verify의 마운트 포인트에 자동으로 등록됩니다. 웹 콘솔에서 해당 플러그인 플래그를 활성화하거나, 설정에서 지정하세요:

```python
from quintet_verify import PublicState, QuintetState

state = QuintetState(
    public=PublicState(
        task="...",
        flags={
            "plugin_a": True,   # 플러그인 A 활성화
            "plugin_b": False,  # 플러그인 B 비활성화
            # ...
        }
    )
)
```

---

<a id="relationship-with-the-main-framework"></a>

## 메인 프레임워크와의 관계

 Quintet-Verify (핵심) qv-extras (이 패키지)
핵심 5역할 견제와 균형 ✅ 핵심 기능 ❌ 관여하지 않음
3대 철칙 ✅ 핵심 기능 ❌ 관여하지 않음
인지 강화 플러그인 ❌ 미포함 ✅ 이 패키지에서 제공
의존성 독립적으로 실행되며 이 패키지에 의존하지 않음 메인 프레임워크에 의존 (런타임에 마운트 포인트 감지)

이 패키지는 메인 프레임워크의 선택적 강화 계층이며, 필수 구성 요소가 아닙니다.

---

<a id="theoretical-origins-and-independence-statement"></a>

## 이론적 기원과 독립성 선언

qv-extras의 일부 메커니즘 설계(결론 이전 브리징, 브로드캐스트 허브, 행동으로서의 메타인지 제어)는 J‑Space Cognition Suite V3.6(doi:10.5281/zenodo.21971181)에서 영감을 받았으며, 그 “Dense Track” 개념과 인지 마커(✓/?/✗)를 참고했습니다.

그러나 이 저장소의 모든 코드는 독자적으로 구현된 것이며, J‑Space의 소스 코드, 프롬프트 템플릿, 프로토콜 문서를 일절 복사하거나 번역하지 않았습니다. Apache License 2.0의 “derivative work” 정의에 따르면, 표준화된 인터페이스를 통해 호출되는 독립 모듈인 이 플러그인 패키지는 J‑Space의 derivative work나 포크에 해당하지 않습니다.

J‑Space 팀의 원저 작업에 대해 존중과 감사를 표하며, 독자 여러분께서는 이 플러그인의 설계 배경을 이해하는 데 유용한 비교 참고 자료로 참조하시길 권합니다.

Quintet-Verify 메인 프레임워크의 전체 이론적 기원과 독립성 선언은 메인 저장소의 README를 참조하세요.

---

<a id="license"></a>

## 라이선스

이 프로젝트는 메인 프레임워크와 동일한 라이선스인 Apache License 2.0을 채택합니다.

자세한 내용은 LICENSE 파일을 참조하세요.

---

<a id="related-links"></a>

## 관련 링크

· Quintet-Verify 메인 프레임워크 – 멀티 에이전트 인지 제어 프레임워크
· J‑Space Cognition Suite V3.6 – 단일 모델 인지 관리
