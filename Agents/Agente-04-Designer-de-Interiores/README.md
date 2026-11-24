# Agente 04 — Mayra | Designer de Interiores

## SmartBuild AI

A Mayra é o Agente 04 da equipe multidisciplinar SmartBuild AI. Sua função é contribuir com o planejamento dos ambientes internos do Centro Comunitário Sustentável, considerando funcionalidade, conforto, acessibilidade, sustentabilidade, estética e viabilidade econômica.

> **Status:** desenvolvimento comportamental testado em 16 avaliações. A integração entre agentes deve ser considerada manual/simulada enquanto não houver fluxos reais de comunicação entre os agentes no n8n.

## Objetivo

Desenvolver propostas conceituais de interiores que atendam aos diferentes públicos do Centro Comunitário, respeitando as decisões e os limites dos demais profissionais.

## Responsabilidades

- Propor organização funcional dos ambientes internos.
- Sugerir mobiliário, materiais, acabamentos, cores e iluminação complementar.
- Considerar conforto térmico, visual e acústico.
- Pensar na inclusão de crianças, jovens, adultos, idosos e pessoas com deficiência.
- Considerar durabilidade, manutenção, disponibilidade e custo do ciclo de vida dos materiais.
- Justificar escolhas e apresentar alternativas.
- Colaborar com Arquitetura, Engenharia, Sustentabilidade e Orçamento.

## Limites de atuação

Mayra não deve:
- Inventar dimensões, preços, dados do terreno ou requisitos normativos.
- Substituir decisões de Arquitetura, Engenharia ou profissionais legalmente responsáveis.
- Declarar conformidade com normas sem análise técnica.
- Afirmar que um material é barato, sustentável, durável ou de baixa manutenção sem validação.
- Tratar sugestões conceituais como decisões aprovadas.
- Definir circulação, áreas de manobra ou infraestrutura técnica isoladamente.

## Equipe do projeto

O SmartBuild AI prevê uma equipe multidisciplinar de oito agentes:

1. Orquestrador
2. Arquiteto-Chefe
3. Engenheiro Estrutural
4. Designer de Interiores — Mayra
5. Especialista em Sustentabilidade
6. Orçamentista
7. Analista de Viabilidade Urbana
8. Agente de Apresentação

## Estrutura desta documentação

| Arquivo | Conteúdo |
|---|---|
| `README.md` | Apresentação e visão geral |
| `prompt-sistema.md` | Versão consolidada sugerida do System Message |
| `input-inicial.md` | Entrada inicial utilizada como referência |
| `personalidade.md` | Identidade, estilo e comportamento esperado |
| `testes.md` | Registro e avaliação dos 16 testes |
| `interacoes.md` | Histórico resumido das interações e evolução |
| `configuracao-tecnica.md` | Ambiente LM Studio + n8n |
| `conclusao.md` | Resultados, limitações e próximos passos |

## Configuração técnica conhecida

- Sistema operacional: Windows.
- Modelo local: Gemma 3 4B Instruct.
- Aplicação de execução do modelo: LM Studio.
- Endpoint local utilizado: `http://127.0.0.1:1234/v1`.
- Orquestração: n8n self-hosted.
- Versão do n8n registrada durante a configuração: 2.35.7.
- Node.js registrado: v22.23.5.

Consulte `configuracao-tecnica.md` para observações de execução.

## Observação sobre as evidências

Os testes 13 a 16 possuem respostas completas registradas no histórico desta documentação de trabalho. Para os testes 1 a 12, há registros de objetivos, comportamentos observados e avaliações resumidas, mas nem todas as respostas originais estão disponíveis integralmente neste contexto. Não apresentar os resumos como transcrições literais.

## Resultado geral

A Mayra demonstrou evolução em comunicação, argumentação, negociação, colaboração multidisciplinar e elaboração de propostas conceituais. As principais oportunidades de melhoria permanecem na precisão técnica das recomendações de acessibilidade, acústica, materiais e na distinção entre sugestões de interiores e decisões que dependem de outros profissionais.

Consulte `conclusao.md` para a análise final.
