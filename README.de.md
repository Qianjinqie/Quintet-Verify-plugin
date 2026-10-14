[English](README.md) | [简体中文](README.zh-CN.md) | [日本語](README.ja.md) | [한국어](README.ko.md) | [Español](README.es.md) | [Français](README.fr.md) | **Deutsch** | [Português (BR)](README.pt-BR.md) | [Русский](README.ru.md)</p>

# Quintet-Verify-plugin

Quintet-Verify-Plugin-Paket zur kognitiven Verbesserung – erweitert das Fünf-Rollen-Verhalten über standardisierte Einhängepunkte, ohne in den Kern-Workflow einzugreifen.

## Inhaltsverzeichnis

- [Projektpositionierung](#project-positioning)
- [Designphilosophie](#design-philosophy)
- [Schnellstart](#quick-start)
  - [Installation](#installation)
  - [Verwendung](#usage)
- [Beziehung zum Hauptframework](#relationship-with-the-main-framework)
- [Theoretische Ursprünge und Unabhängigkeitserklärung](#theoretical-origins-and-independence-statement)
- [Lizenz](#license)
- [Verwandte Links](#related-links)

---

<a id="project-positioning"></a>
## Projektpositionierung

qv-extras ist ein optionales Erweiterungspaket für Quintet-Verify. Es bietet eine Sammlung von Plugins zur kognitiven Verbesserung, die über die standardisierten Einhängepunkte pre_act_hooks / post_act_hooks injiziert werden, die das Hauptframework bereitstellt.

Alle Plugins sind standardmäßig deaktiviert – Benutzer aktivieren sie bei Bedarf über die Web-Konsole oder die Konfiguration. Das Kernframework bleibt von Plugins unberührt; ohne dieses Paket bleibt der volle Funktionsumfang von Quintet-Verify erhalten.

---

<a id="design-philosophy"></a>
## Designphilosophie

- Nicht-invasiv – verändert den Kerncode von Quintet-Verify nicht; injiziert ausschließlich über die Einhängepunkte.  
- Aktivierung bei Bedarf – alle Plugins sind standardmäßig deaktiviert; Benutzer schalten sie je nach Aufgabenanforderungen gezielt ein.  
- Kombinierbar – die Plugins sind voneinander unabhängig und können in beliebiger Kombination eingesetzt werden.

---

<a id="quick-start"></a>
## Schnellstart

<a id="installation"></a>
### Installation

Direkt aus dem Quellcode installieren:

```bash
git clone https://github.com/Qianjinqie/Quintet-Verify-plugin.git
cd Quintet-Verify-plugin
pip install .
```

<a id="usage"></a>

### Verwendung

Nach der Installation werden die Plugins automatisch bei den Einhängepunkten von Quintet-Verify registriert. Aktivieren Sie die entsprechenden Plugin-Flags in der Web-Konsole oder setzen Sie sie in der Konfiguration:

```python
from quintet_verify import PublicState, QuintetState

state = QuintetState(
    public=PublicState(
        task="...",
        flags={
            "plugin_a": True,   # Plugin A aktivieren
            "plugin_b": False,  # Plugin B deaktivieren
            # ...
        }
    )
)
```

---

<a id="relationship-with-the-main-framework"></a>

## Beziehung zum Hauptframework

 Quintet-Verify (Kern) qv-extras (dieses Paket)
Fünf-Rollen-Checks & Balances des Kerns ✅ Kernfunktionalität ❌ nicht beteiligt
Drei eiserne Regeln ✅ Kernfunktionalität ❌ nicht beteiligt
Plugins zur kognitiven Verbesserung ❌ nicht enthalten ✅ von diesem Paket bereitgestellt
Abhängigkeit Läuft eigenständig, hängt nicht von diesem Paket ab Hängt vom Hauptframework ab (erkennt die Einhängepunkte zur Laufzeit)

Dieses Paket ist eine optionale Erweiterungsschicht für das Hauptframework, keine zwingend erforderliche Komponente.

---

<a id="theoretical-origins-and-independence-statement"></a>

## Theoretische Ursprünge und Unabhängigkeitserklärung

Einige Mechanismusentwürfe in qv-extras (Brückenbildung vor der Schlussfolgerung, Broadcast-Hub, metakognitive Steuerung als Aktion) sind von J‑Space Cognition Suite V3.6 (doi:10.5281/zenodo.21971181) inspiriert und greifen dessen Konzepte von „Dense Track“ und kognitiven Markern (✓/?/✗) auf.

Der gesamte Code in diesem Repository wurde jedoch unabhängig implementiert; es wurde kein Quellcode, keine Prompt-Vorlagen und keine Protokolltexte von J‑Space kopiert oder übersetzt. Nach der Definition von „derivative work“ in der Apache License 2.0 stellt dieses Plugin-Paket – als unabhängiges Modul, das über standardisierte Schnittstellen aufgerufen wird – kein abgeleitetes Werk und keinen Fork von J‑Space dar.

Wir bringen dem Team von J‑Space unseren Respekt und unsere Dankbarkeit für die ursprüngliche Arbeit zum Ausdruck und empfehlen den Lesern, es als nützliche vergleichende Referenz zum Verständnis des Designhintergrunds dieses Plugins heranzuziehen.

Die vollständige Darlegung der theoretischen Ursprünge und der Unabhängigkeit des Quintet-Verify-Hauptframeworks finden Sie im README des Haupt-Repositorys.

---

<a id="license"></a>

## Lizenz

Dieses Projekt verwendet dieselbe Lizenz wie das Hauptframework: Apache License 2.0.

Details finden Sie in der Datei LICENSE.

---

<a id="related-links"></a>

## Verwandte Links

· Quintet-Verify-Hauptframework – Multi-Agenten-Framework zur kognitiven Kontrolle
· J‑Space Cognition Suite V3.6 – Kognitives Management mit einem einzelnen Modell
