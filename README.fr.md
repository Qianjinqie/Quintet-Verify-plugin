<p align="right">[English](README.md) | [简体中文](README.zh-CN.md) | [日本語](README.ja.md) | [한국어](README.ko.md) | [Español](README.es.md) | **Français** | [Deutsch](README.de.md) | [Português (BR)](README.pt-BR.md) | [Русский](README.ru.md)</p>

# Quintet-Verify-plugin

Pack de plugins d'amélioration cognitive Quintet-Verify – étend le comportement des cinq rôles via des points de montage standardisés, sans s'immiscer dans le flux de travail central.

## Table des matières

- [Positionnement du projet](#project-positioning)
- [Philosophie de conception](#design-philosophy)
- [Démarrage rapide](#quick-start)
  - [Installation](#installation)
  - [Utilisation](#usage)
- [Relation avec le framework principal](#relationship-with-the-main-framework)
- [Origines théoriques et déclaration d'indépendance](#theoretical-origins-and-independence-statement)
- [Licence](#license)
- [Liens connexes](#related-links)

---

<a id="project-positioning"></a>
## Positionnement du projet

qv-extras est un paquet d'extensions optionnel pour Quintet-Verify. Il fournit un ensemble de plugins d'amélioration cognitive injectés via les points de montage standardisés pre_act_hooks / post_act_hooks exposés par le framework principal.

Tous les plugins sont désactivés par défaut – les utilisateurs les activent à la demande via la console Web ou la configuration. Le framework central n'est pas affecté par les plugins ; sans ce paquet, l'intégralité des fonctionnalités de Quintet-Verify reste intacte.

---

<a id="design-philosophy"></a>
## Philosophie de conception

- Non‑intrusif – ne modifie pas le code central de Quintet-Verify ; injecte uniquement via les points de montage.  
- Activation à la demande – tous les plugins sont désactivés par défaut ; les utilisateurs les activent de manière sélective selon les besoins de la tâche.  
- Composable – les plugins sont indépendants les uns des autres et peuvent être utilisés dans n'importe quelle combinaison.

---

<a id="quick-start"></a>
## Démarrage rapide

<a id="installation"></a>
### Installation

Installez directement depuis les sources :

```bash
git clone https://github.com/Qianjinqie/Quintet-Verify-plugin.git
cd Quintet-Verify-plugin
pip install .
```

<a id="usage"></a>

### Utilisation

Après l'installation, les plugins sont automatiquement enregistrés auprès des points de montage de Quintet-Verify. Activez les drapeaux de plugins correspondants dans la console Web, ou définissez-les dans la configuration :

```python
from quintet_verify import PublicState, QuintetState

state = QuintetState(
    public=PublicState(
        task="...",
        flags={
            "plugin_a": True,   # activer le plugin A
            "plugin_b": False,  # désactiver le plugin B
            # ...
        }
    )
)
```

---

<a id="relationship-with-the-main-framework"></a>

## Relation avec le framework principal

 Quintet-Verify (noyau) qv-extras (ce paquet)
Contrôles et contrepoids des cinq rôles du noyau ✅ capacité du noyau ❌ non concerné
Trois règles de fer ✅ capacité du noyau ❌ non concerné
Plugins d'amélioration cognitive ❌ non inclus ✅ fournis par ce paquet
Dépendance S'exécute de manière indépendante, ne dépend pas de ce paquet Dépend du framework principal (détecte les points de montage à l'exécution)

Ce paquet est une couche d'amélioration optionnelle pour le framework principal, et non un composant requis.

---

<a id="theoretical-origins-and-independence-statement"></a>

## Origines théoriques et déclaration d'indépendance

Certaines conceptions de mécanismes de qv-extras (pontage pré‑conclusion, hub de diffusion, contrôle métacognitif en tant qu'action) sont inspirées de J‑Space Cognition Suite V3.6 (doi:10.5281/zenodo.21971181), en s'appuyant sur ses concepts de « Dense Track » et de marqueurs cognitifs (✓/?/✗).

Cependant, tout le code de ce dépôt est implémenté de manière indépendante ; aucun code source, modèle de prompt ni texte de protocole de J‑Space n'a été copié ni traduit. Selon la définition d'« œuvre dérivée » de la licence Apache License 2.0, ce paquet de plugins – en tant que module indépendant invoqué via des interfaces standardisées – ne constitue ni une œuvre dérivée ni un fork de J‑Space.

Nous exprimons notre respect et notre gratitude à l'équipe de J‑Space pour son travail original, et recommandons aux lecteurs de s'y référer comme à une référence comparative utile pour comprendre le contexte de conception de ce plugin.

Pour la déclaration complète des origines théoriques et de l'indépendance du framework principal Quintet-Verify, veuillez consulter le README du dépôt principal.

---

<a id="license"></a>

## Licence

Ce projet adopte la même licence que le framework principal : Apache License 2.0.

Consultez le fichier LICENSE pour plus de détails.

---

<a id="related-links"></a>

## Liens connexes

· Framework principal Quintet-Verify – Framework de contrôle cognitif multi‑agents
· J‑Space Cognition Suite V3.6 – Gestion cognitive mono‑modèle
