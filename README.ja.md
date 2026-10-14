[English](README.en.md) | [简体中文](README.md) | **日本語** | [한국어](README.ko.md) | [Español](README.es.md) | [Français](README.fr.md) | [Deutsch](README.de.md) | [Português (BR)](README.pt-BR.md) | [Русский](README.ru.md)

# Quintet-Verify-plugin

Quintet-Verify 認知強化プラグインパック – コアワークフローに侵入することなく、標準化されたマウントポイントを通じて五役の挙動を拡張します。

## 目次

- [プロジェクトの位置付け](#project-positioning)
- [設計思想](#design-philosophy)
- [クイックスタート](#quick-start)
  - [インストール](#installation)
  - [使い方](#usage)
- [メインフレームワークとの関係](#relationship-with-the-main-framework)
- [理論的由来および独立性に関する声明](#theoretical-origins-and-independence-statement)
- [ライセンス](#license)
- [関連リンク](#related-links)

---

<a id="project-positioning"></a>
## プロジェクトの位置付け

qv-extras は、Quintet-Verify のオプション拡張パッケージです。メインフレームワークが公開している標準化された pre_act_hooks / post_act_hooks マウントポイントを介して注入される、一連の認知強化プラグインを提供します。

すべてのプラグインはデフォルトでオフになっており、ユーザーは Web コンソールまたは設定から必要に応じて有効化します。コアフレームワークはプラグインの影響を受けません。本パッケージがなくても、Quintet-Verify の全機能は損なわれずに動作します。

---

<a id="design-philosophy"></a>
## 設計思想

- 非侵入型 – Quintet-Verify のコアコードを変更せず、マウントポイントを通じてのみ注入します。  
- オンデマンド有効化 – すべてのプラグインはデフォルトでオフです。ユーザーはタスクの要件に応じて選択的に有効化します。  
- 組み合わせ可能 – プラグインは互いに独立しており、任意の組み合わせで利用できます。

---

<a id="quick-start"></a>
## クイックスタート

<a id="installation"></a>
### インストール

ソースから直接インストールします：

```bash
git clone https://github.com/Qianjinqie/Quintet-Verify-plugin.git
cd Quintet-Verify-plugin
pip install .
```

<a id="usage"></a>

### 使い方

インストール後、プラグインは自動的に Quintet-Verify のマウントポイントへ登録されます。Web コンソールで対応するプラグインフラグを有効にするか、設定で指定してください：

```python
from quintet_verify import PublicState, QuintetState

state = QuintetState(
    public=PublicState(
        task="...",
        flags={
            "plugin_a": True,   # プラグイン A を有効化
            "plugin_b": False,  # プラグイン B を無効化
            # ...
        }
    )
)
```

---

<a id="relationship-with-the-main-framework"></a>

## メインフレームワークとの関係

 Quintet-Verify（コア） qv-extras（本パッケージ）
コアの五役チェック・アンド・バランス ✅ コア機能 ❌ 関与しない
三つの鉄則 ✅ コア機能 ❌ 関与しない
認知強化プラグイン ❌ 同梱されない ✅ 本パッケージが提供
依存関係 単独で動作し、本パッケージには依存しない メインフレームワークに依存（実行時にマウントポイントを検出）

本パッケージはメインフレームワークのオプションの拡張レイヤーであり、必須コンポーネントではありません。

---

<a id="theoretical-origins-and-independence-statement"></a>

## 理論的由来および独立性に関する声明

qv-extras の一部のメカニズム設計（結論前ブリッジング、ブロードキャストハブ、アクションとしてのメタ認知制御）は、J‑Space Cognition Suite V3.6（doi:10.5281/zenodo.21971181）から着想を得たものであり、その「Dense Track」および認知マーカー（✓/?/✗）の概念を参考にしています。

ただし、本リポジトリのすべてのコードは独自に実装されたものであり、J‑Space のソースコード、プロンプトテンプレート、プロトコル文書を複製または翻訳したものは一切含まれていません。Apache License 2.0 の「派生著作物」の定義において、本プラグインパッケージは、標準化されたインターフェースを介して呼び出される独立したモジュールであり、J‑Space の派生著作物やフォークには該当しません。

J‑Space チームのオリジナルな仕事に敬意と感謝を表します。また、本プラグインの設計背景を理解するための有益な比較参考資料として、読者の皆様にも参照をお勧めします。

Quintet-Verify メインフレームワークの完全な理論的由来および独立性に関する声明については、メインリポジトリの README をご参照ください。

---

<a id="license"></a>

## ライセンス

本プロジェクトは、メインフレームワークと同じライセンスである Apache License 2.0 を採用しています。

詳細は LICENSE ファイルをご覧ください。

---

<a id="related-links"></a>

## 関連リンク

· Quintet-Verify メインフレームワーク – マルチエージェントによる認知制御フレームワーク
· J‑Space Cognition Suite V3.6 – シングルモデルの認知管理
