[English](README.en.md) | [简体中文](README.md) | [日本語](README.ja.md) | [한국어](README.ko.md) | **Español** | [Français](README.fr.md) | [Deutsch](README.de.md) | [Português (BR)](README.pt-BR.md) | [Русский](README.ru.md)

# Quintet-Verify-plugin

Paquete de plugins de mejora cognitiva de Quintet-Verify – extiende el comportamiento de los cinco roles mediante puntos de montaje estandarizados, sin invadir el flujo de trabajo central.

## Tabla de contenidos

- [Posicionamiento del proyecto](#project-positioning)
- [Filosofía de diseño](#design-philosophy)
- [Inicio rápido](#quick-start)
  - [Instalación](#installation)
  - [Uso](#usage)
- [Relación con el framework principal](#relationship-with-the-main-framework)
- [Orígenes teóricos y declaración de independencia](#theoretical-origins-and-independence-statement)
- [Licencia](#license)
- [Enlaces relacionados](#related-links)

---

<a id="project-positioning"></a>
## Posicionamiento del proyecto

qv-extras es un paquete de extensión opcional para Quintet-Verify. Proporciona un conjunto de plugins de mejora cognitiva que se inyectan a través de los puntos de montaje estandarizados pre_act_hooks / post_act_hooks expuestos por el framework principal.

Todos los plugins están desactivados por defecto – los usuarios los activan a demanda mediante la consola web o la configuración. El framework central no se ve afectado por los plugins; sin este paquete, la funcionalidad completa de Quintet-Verify permanece intacta.

---

<a id="design-philosophy"></a>
## Filosofía de diseño

- No invasivo – no modifica el código central de Quintet-Verify; se inyecta únicamente a través de los puntos de montaje.  
- Activación a demanda – todos los plugins están desactivados por defecto; los usuarios los activan selectivamente según los requisitos de la tarea.  
- Combinables – los plugins son independientes entre sí y pueden usarse en cualquier combinación.

---

<a id="quick-start"></a>
## Inicio rápido

<a id="installation"></a>
### Instalación

Instalar directamente desde el código fuente:

```bash
git clone https://github.com/Qianjinqie/Quintet-Verify-plugin.git
cd Quintet-Verify-plugin
pip install .
```

<a id="usage"></a>

### Uso

Tras la instalación, los plugins se registran automáticamente en los puntos de montaje de Quintet-Verify. Active las flags correspondientes en la consola web, o establézcalas en la configuración:

```python
from quintet_verify import PublicState, QuintetState

state = QuintetState(
    public=PublicState(
        task="...",
        flags={
            "plugin_a": True,   # habilitar el plugin A
            "plugin_b": False,  # deshabilitar el plugin B
            # ...
        }
    )
)
```

---

<a id="relationship-with-the-main-framework"></a>

## Relación con el framework principal

 Quintet-Verify (núcleo) qv-extras (este paquete)
Pesos y contrapesos de los cinco roles del núcleo ✅ capacidad central ❌ no involucrado
Tres reglas de hierro ✅ capacidad central ❌ no involucrado
Plugins de mejora cognitiva ❌ no incluidos ✅ proporcionados por este paquete
Dependencia Se ejecuta de forma independiente, no depende de este paquete Depende del framework principal (detecta los puntos de montaje en tiempo de ejecución)

Este paquete es una capa de mejora opcional para el framework principal, no un componente obligatorio.

---

<a id="theoretical-origins-and-independence-statement"></a>

## Orígenes teóricos y declaración de independencia

Algunos diseños de mecanismos de qv-extras (puenteo preconclusión, hub de difusión, control metacognitivo como acción) están inspirados en J‑Space Cognition Suite V3.6 (doi:10.5281/zenodo.21971181), basándose en sus conceptos de “Dense Track” y de marcadores cognitivos (✓/?/✗).

Sin embargo, todo el código de este repositorio está implementado de forma independiente; no se ha copiado ni traducido ningún código fuente, plantilla de prompts ni texto de protocolo de J‑Space. Según la definición de “obra derivada” de la Apache License 2.0, este paquete de plugins – como módulo independiente invocado a través de interfaces estandarizadas – no constituye una obra derivada ni un fork de J‑Space.

Expresamos nuestro respeto y gratitud al equipo de J‑Space por su trabajo original, y recomendamos a los lectores consultarlo como una referencia comparativa útil para comprender el trasfondo de diseño de este plugin.

Para conocer los orígenes teóricos completos y la declaración de independencia del framework principal Quintet-Verify, consulte el README del repositorio principal.

---

<a id="license"></a>

## Licencia

Este proyecto adopta la misma licencia que el framework principal: Apache License 2.0.

Consulte el archivo LICENSE para más detalles.

---

<a id="related-links"></a>

## Enlaces relacionados

· Framework principal de Quintet-Verify – Framework de control cognitivo multiagente
· J‑Space Cognition Suite V3.6 – Gestión cognitiva de modelo único
