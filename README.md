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

O documento completo do projeto está disponível [neste PDF](Estudos_Agente_Blip.pdf)

`blip-agente/Estudos_BlIP_Agente.pdf`

---

## 📑 Índice resumido do documento

# Índice do Projeto — Agente Inteligente BLiP

1. **Introdução**
2. **O que aprendi sobre o BLiP**
3. **Automação de Conversas (Builder / Fluxo Visual)**
4. **Agentes Inteligentes — IA integrada ao fluxo**
5. **Ecossistema de Canais**
   5.1. APIs poderosas e flexíveis  
   5.2. Integração com sistemas externos  
   5.3. Métricas, relatórios e monitoramento
6. **Experiência prática**
7. **Antes de tudo: Rascunho no papel**
8. **Uso de IA para análise e melhoria do fluxo**
9. **Estruturação no BLiP**
10. **Diálogos por fase**
11. **Fluxo completo em Mermaid**
12. **Resultados práticos do projeto**
13. **Visualização do Fluxo no BLiP**
14. **Conclusão**
15. **Referências**


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
%%{init: {'flowchart': {'layout': 'adaptive'}}}%%
flowchart TB
    A0(["Início"]) --> A1["1.0 Boas-vindas"]
    A1 --> A2{"1.1 Tem cadastro?"}
    A2 -- Sim --> B1["2.0 Inserir CPF"]
    A2 -- Não --> C1["3.0 Cadastro Rápido"]
    C1 --> C2["3.1 Inserir Nome"]
    C2 --> C3["3.2 Inserir Telefone"]
    C3 --> C4["3.3 Inserir CPF"]
    C4 --> C5["3.4 Validar CPF"]
    C5 --> C6["3.5 CPF Válido"]
    C6 --> C7["3.6 Inserir E-mail"]
    C7 --> C8["3.7 Inserir Data Nascimento"]
    C8 --> C9["3.8 Inserir Endereço"]
    C9 --> C10{"3.9 Confirma Cadastro?"}
    C10 -- Sim --> C11["3.10 Envio SMS"]
    C10 -- Não --> C12["3.11 Envio E-mail"]
    C11 --> C13["3.12 Validação Código"]
    C12 --> C13
    C13 --> B1
    B1 --> B2["2.1 Confirmar CPF"]
    B2 --> B3["2.2 Analisando CPF"]
    B3 -- Não localizado --> B4["2.3 Inserir CPF novamente"]
    B4 --> B1
    B3 -- Localizado --> M0["5.0 Menu Principal"]
    M0 --> M1["5.1 Informações do Pedido"] & M2["5.2 Dados do Cliente"] & M3["5.3 Reclamações"] & M4["5.4 Agendar Entrega"] & H4["6.4 Atendimento Humano"] & H5["6.5 Encerrar Atendimento"]
    M1 --> P1["6.1 Consultar Pedido"]
    P1 --> P2["6.2 Status da Entrega"]
    P2 --> M0 & P3["6.3 Valor e Detalhes"] & H5 & H4
    P3 --> H5 & H4 & M0
    M2 --> D1["7.1 Informações Pessoais"]
    D1 --> D2["7.3 Editar Dados do Cliente"] & M0 & H5 & H4
    D2 --> E0["7.4 Escolher Campo"]
    E0 --> E1["7.4.1 Nome"] & E2["7.4.2 Data Nascimento"] & E3["7.4.3 Editar CPF"] & E4["7.4.4 Editar Telefone"] & E5["7.4.5 Editar Endereço"] & M0
    E5 --> ER1["7.4.6 Rua/Avenida"]
    ER1 --> ER2["7.4.7 Número"]
    ER2 --> ER3["7.4.8 Complemento"]
    ER3 --> ER4["7.4.9 Bairro"]
    ER4 --> ER5["7.4.10 Cidade"]
    ER5 --> ER6["7.4.11 Estado"]
    ER6 --> ER7["7.4.12 CEP"]
    ER7 --> ER8["7.4.13 Dados Atualizados"]
    ER8 --> M0 & H4
    H4 --> HA["10.0 Cancelamento"] & HB["10.1 Solucionar Problema"] & HC["10.2 Finalizar Atendimento Humano"]
    HA --> H5
    HB --> H5
    HC --> S0["11.0 Pesquisa de Satisfação"]
    S0 --> S1["11.1 Muito Satisfeito"] & S2["11.2 Satisfeito"] & S3["11.3 Neutro"] & S4["11.4 Insatisfeito"] & S5["11.5 Muito Insatisfeito"]
    S1 --> S6["12.0 Encerrar Atendimento"]
    S2 --> S6
    S3 --> S6 & H4
    S4 --> S6 & H4
    S5 --> S6 & H4
    S6 --> H5
    M3 --> R0["8.0 Acompanhar/Mudar Pedido"] & R1["Dúvidas do Produto"] & R2["Pagamento"] & R3["Reclamações"] & R4["Meu Cadastro"] & R5["Atendimento Humano"] & M0 & H5
    R1 --> H4
    R2 --> H4
    R3 --> H4
    R4 --> M2
    R5 --> H4
    R0 --> S01["Status → Consultar Pedido"] & S02["8.1 Rastreio"] & S03["Cancelar Pedido"] & S04["Trocar Produto"] & M0 & H5
    S01 --> P1
    S02 --> M1
    S03 --> H4
    S04 --> H4

    S04 --> H4

    M1 --> M2["12.2 - Deseja voltar ao menu?"]
    M2 --> D1 & M3["12.3 - Fim do fluxo"]
    R1["4.0 - Reservado"]
