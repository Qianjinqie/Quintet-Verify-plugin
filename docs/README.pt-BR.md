[English](README.en.md) | [简体中文](../README.md) | [日本語](README.ja.md) | [한국어](README.ko.md) | [Español](README.es.md) | [Français](README.fr.md) | [Deutsch](README.de.md) | **Português (BR)** | [Русский](README.ru.md)

# Quintet-Verify-plugin

Pacote de plugins de aprimoramento cognitivo do Quintet-Verify – estende o comportamento dos cinco papéis por meio de pontos de montagem padronizados, sem invadir o fluxo de trabalho central.

## Sumário

- [Posicionamento do Projeto](#project-positioning)
- [Filosofia de Design](#design-philosophy)
- [Início Rápido](#quick-start)
  - [Instalação](#installation)
  - [Uso](#usage)
- [Relação com o Framework Principal](#relationship-with-the-main-framework)
- [Origens Teóricas e Declaração de Independência](#theoretical-origins-and-independence-statement)
- [Licença](#license)
- [Links Relacionados](#related-links)

---

<a id="project-positioning"></a>
## Posicionamento do Projeto

qv-extras é um pacote de extensão opcional para o Quintet-Verify. Ele fornece um conjunto de plugins de aprimoramento cognitivo que são injetados por meio dos pontos de montagem padronizados pre_act_hooks / post_act_hooks expostos pelo framework principal.

Todos os plugins ficam desativados por padrão – os usuários os habilitam sob demanda via console Web ou configuração. O framework central não é afetado pelos plugins; sem este pacote, a funcionalidade completa do Quintet-Verify permanece intacta.

---

<a id="design-philosophy"></a>
## Filosofia de Design

- Não invasivo – não modifica o código central do Quintet-Verify; injeta apenas por meio dos pontos de montagem.  
- Habilitação sob demanda – todos os plugins ficam desativados por padrão; os usuários os ativam seletivamente conforme os requisitos da tarefa.  
- Componível – os plugins são independentes entre si e podem ser usados em qualquer combinação.

---

<a id="quick-start"></a>
## Início Rápido

<a id="installation"></a>
### Instalação

Instale diretamente a partir do código-fonte:

```bash
git clone https://github.com/Qianjinqie/Quintet-Verify-plugin.git
cd Quintet-Verify-plugin
pip install .
```

<a id="usage"></a>

### Uso

Após a instalação, os plugins são registrados automaticamente nos pontos de montagem do Quintet-Verify. Habilite as flags de plugin correspondentes no console Web, ou defina-as na configuração:

```python
from quintet_verify import PublicState, QuintetState

state = QuintetState(
    public=PublicState(
        task="...",
        flags={
            "plugin_a": True,   # habilita o plugin A
            "plugin_b": False,  # desabilita o plugin B
            # ...
        }
    )
)
```

---

<a id="relationship-with-the-main-framework"></a>

## Relação com o Framework Principal

 Quintet-Verify (núcleo) qv-extras (este pacote)
Freios e contrapesos dos cinco papéis no núcleo ✅ capacidade do núcleo ❌ não envolvido
Três regras de ferro ✅ capacidade do núcleo ❌ não envolvido
Plugins de aprimoramento cognitivo ❌ não incluído ✅ fornecido por este pacote
Dependência Executa de forma independente, não depende deste pacote Depende do framework principal (detecta os pontos de montagem em tempo de execução)

Este pacote é uma camada de aprimoramento opcional para o framework principal, não um componente obrigatório.

---

<a id="theoretical-origins-and-independence-statement"></a>

## Origens Teóricas e Declaração de Independência

Alguns designs de mecanismos do qv-extras (ponte de pré-conclusão, hub de broadcast, controle metacognitivo como ação) são inspirados no J‑Space Cognition Suite V3.6 (doi:10.5281/zenodo.21971181), com base em seus conceitos de “Dense Track” e de marcadores cognitivos (✓/?/✗).

No entanto, todo o código deste repositório é implementado de forma independente; nenhum código-fonte, modelo de prompt ou texto de protocolo do J‑Space foi copiado ou traduzido. Sob a definição de “derivative work” na Apache License 2.0, este pacote de plugins – como um módulo independente invocado por meio de interfaces padronizadas – não constitui uma obra derivada nem um fork do J‑Space.

Expressamos nosso respeito e gratidão à equipe do J‑Space por seu trabalho original, e recomendamos que os leitores o consultem como uma referência comparativa útil para compreender o contexto de design deste plugin.

Para a declaração completa de origens teóricas e independência do framework principal Quintet-Verify, consulte o README do repositório principal.

---

<a id="license"></a>

## Licença

Este projeto adota a mesma licença do framework principal: Apache License 2.0.

Consulte o arquivo LICENSE para obter detalhes.

---

<a id="related-links"></a>

## Links Relacionados

· Framework principal do Quintet-Verify – Framework de controle cognitivo multiagente
· J‑Space Cognition Suite V3.6 – Gerenciamento cognitivo de modelo único
