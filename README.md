# Projeto BLiP — Agente Inteligente

**Autor:** Roney Cesar  
**Ano:** 2025  

Este repositório reúne estudos e a construção de um **Agente Inteligente** utilizando a plataforma **BLiP**, combinando automação conversacional e suporte de IA generativa (ChatGPT).  

O objetivo do projeto é documentar a jornada de aprendizado, desde os primeiros rascunhos no papel até a implementação final do assistente digital, destacando:  

- Automação de conversas e fluxos visuais no BLiP  
- Agentes inteligentes integrados ao fluxo  
- Integração com múltiplos canais de atendimento  
- Métricas, monitoramento e relatórios  
- Boas práticas de design conversacional e UX  

O documento completo do projeto está disponível [neste PDF](blip-agente/Estudos_Agente_Blip.pdf)

`blip-agente/Estudos_BlIP_Agente.pdf`

---

## 📑 Índice resumido do documento

1. [Introdução](#introdução)  
2. [O que aprendi sobre o BLiP](#o-que-aprendi-sobre-o-blip)  
3. [Automação de Conversas (Builder / Fluxo Visual)](#automação-de-conversas-builder--fluxo-visual)  
4. [Agentes Inteligentes — IA integrada ao fluxo](#agentes-inteligentes-ia-integrada-ao-fluxo)  
5. [Ecossistema de Canais](#ecossistema-de-canais)  
   - 5.1 APIs poderosas e flexíveis  
   - 5.2 Integração com sistemas externos  
   - 5.3 Métricas, relatórios e monitoramento  
6. [Experiência prática](#experiência-prática)  
7. [Antes de tudo: Rascunho no papel](#rascunho-no-papel)  
8. [Uso de IA para análise e melhoria do fluxo](#uso-de-ia-para-análise-e-melhoria-do-fluxo)  
9. [Estruturação no BLiP](#estruturação-no-blip)  
10. [Diálogos por fase](#diálogos-por-fase)  
11. [Fluxo completo em Mermaid](#fluxo-completo-em-mermaid)  
12. [Resultados práticos do projeto](#resultados-práticos-do-projeto)  
13. [Visualização do Fluxo no BLiP](#visualização-do-fluxo-no-blip)  
14. [Conclusão](#conclusão)  
15. [Referências](#referências)

---

## ⚙️ Ferramentas utilizadas

- **BLiP Builder** — Plataforma para criar fluxos conversacionais e automatizar atendimentos.  
- **ChatGPT / IA Generativa** — Suporte para análise, melhoria de diálogos e tomada de decisões no fluxo.  
- **Mermaid** — Ferramenta para modelagem visual do fluxo, permitindo diagramas claros e organizados.  
- **APIs e Integrações** — Conexão com sistemas externos e outros canais de atendimento.  
- **Documentação e Rascunho no Papel** — Planejamento inicial do fluxo antes da implementação digital.  

> Essas ferramentas foram utilizadas para garantir **automação, organização e qualidade** na construção do agente inteligente.

---

## 🎯 Objetivos do projeto

- Compreender a construção de um agente inteligente completo, desde o planejamento até a implementação.  
- Aplicar boas práticas de **design conversacional** e **UX** em fluxos automatizados.  
- Automatizar atendimentos, reduzindo esforço manual e aumentando eficiência.  
- Integrar inteligência artificial para **análise de dados, melhoria de diálogos e personalização** do atendimento.  
- Criar uma estrutura modular e escalável que permita fácil manutenção e evolução do fluxo.  
- Garantir que o agente consiga atender de forma clara, coerente e com qualidade em múltiplos canais.

---

## 📌 Como usar

1. Acesse a pasta [`blip-agente`](blip-agente) no repositório.  
2. Abra o arquivo PDF: `Estudos_Agente_Blip.pdf`

---

## Fluxo completo em Mermaid

```mermaid
---
config:
  layout: elk
---
flowchart TB
    A1["1.0 - Boas-vindas"] --> A2["1.1 - Tem cadastro?"]
    A2 -- "1.1.1 Não" --> B1["3.0 - Cadastro rápido"]
    A2 -- "1.1.2 Sim" --> C1["2.0 - Inserir CPF"]
    C1 --> C2["2.1 - Inserir CPF"]
    C2 --> C3["2.2 - Confirmação CPF"]
    C3 --> C4["2.3 - Analisando CPF"]
    C4 -- "2.3.1 CPF não encontrado" --> C2
    C4 -- "2.3.2 CPF localizado" --> D1["5.0 - Menu Principal"]
    B1 --> B2["3.1 - Inserir nome"]
    B2 --> B3["3.2 - Inserir telefone"]
    B3 --> B4["3.3 - Inserir CPF"]
    B4 --> B5["3.4 - Validar CPF"]
    B5 -- "3.4.1 CPF inválido" --> B4
    B5 -- "3.4.2 CPF válido" --> B5a["3.5 - CPF válido"]
    B5a --> B6["3.6 - Inserir e-mail"]
    B6 --> B7["3.7 - Inserir data de nascimento"]
    B7 --> B8["3.8 - Inserir endereço"]
    B8 --> B9["3.9 - Confirmação cadastro"]
    B9 -- Sim --> B10["3.10 - Envio SMS"]
    B9 -- Não --> B11["3.11 - Envio e-mail"]
    B10 --> B12["3.12 - Validação código"]
    B11 --> B12
    B12 --> C1
    D1 --> E1["5.1 - Informações do Pedido"] & E2["5.2 - Dados do Cliente"] & E3["5.3 - Suporte Técnico"] & E4["5.4 - Agendamento de Entrega"] & E5["5.5 - Atendimento Humano"]
    E1 --> F1["6.1 - Consultar pedido"]
    F1 --> F2["6.2 - Status da entrega"]
    F2 --> F3["6.3 - Valor e detalhes"]
    F3 --> D1 & F4["6.4 - Atendimento humano"] & F5["6.5 - Encerrar atendimento"]
    E2 --> G1["7.1 - Informações pessoais"]
    G1 --> G2["7.2 - Endereço"]
    G2 --> D1 & F4 & F5
    E3 --> H1["8.1 - Coleta do problema"]
    H1 --> H2["8.2 - Sugestão automática"]
    H2 --> H3{"8.3 - Problema resolvido?"}
    H3 -- Sim --> D1
    H3 -- Não --> F4
    E4 --> I1["9.1 - Selecionar data"]
    I1 --> I2["9.2 - Confirmar agendamento"]
    I2 --> D1
    E5 --> J1["10.1 - Motivo do contato"]
    J1 --> J2["10.2 - Cancelamento ou resolução"]
    J2 --> J3["10.3 - Final atendimento humano"]
    J3 --> K1["11.0 - Pesquisa de satisfação"]
    K1 -- "11.1 Muito satisfeito" --> L1["12.0 - Encerrar atendimento"]
    K1 -- "11.2 Satisfeito" --> L1
    K1 -- "11.3 Neutro" --> L1
    K1 -- "11.4 Insatisfeito" --> L1
    K1 -- "11.5 Muito insatisfeito" --> L1
    L1 --> M1["12.1 - Agradecimento"]
    M1 --> M2["12.2 - Deseja voltar ao menu?"]
    M2 --> D1 & M3["12.3 - Fim do fluxo"]
    R1["4.0 - Reservado"]
