# 🏗️ SmartBuild AI

### Inteligência Artificial colaborativa para o planejamento de espaços sustentáveis.

<p align="center">
  <strong>Construindo ideias, conectando inteligências.</strong>
</p>

<p align="center">
 • 🤖 Inteligência Artificial • 🏗️ Inovação
</p>

---

## 🌱 Sobre o projeto

O **SmartBuild AI** é um projeto acadêmico que utiliza agentes de Inteligência Artificial especializados para auxiliar no planejamento de um Centro Comunitário Sustentável.

A proposta consiste em desenvolver uma equipe de agentes com funções específicas, capazes de analisar problemas, propor soluções e colaborar entre diferentes áreas profissionais.

Por meio dessa abordagem, buscamos demonstrar como a Inteligência Artificial pode contribuir para o desenvolvimento de projetos que considerem sustentabilidade, acessibilidade, conforto, funcionalidade e viabilidade econômica.

## 🎯 Objetivos

- Desenvolver uma equipe de agentes de IA especializados.
- Simular a colaboração entre diferentes áreas profissionais.
- Automatizar tarefas utilizando fluxos de trabalho.
- Explorar a comunicação entre agentes de Inteligência Artificial.
- Desenvolver propostas para um Centro Comunitário Sustentável.
- Avaliar a eficiência e as limitações dos agentes.

## 🤖 Equipe de agentes

O SmartBuild AI conta com oito agentes especializados:

| Nº | Agente | Responsabilidade |
|:---:|---|---|
| 01 | Orquestrador | Coordenar tarefas e integrar os agentes. |
| 02 | Arquiteto-Chefe | Planejamento arquitetônico e organização dos espaços. |
| 03 | Engenheiro Estrutural | Análise e soluções estruturais. |
| 04 | Mayra — Designer de Interiores | Conforto, estética, mobiliário e organização interna. |
| 05 | Especialista em Sustentabilidade | Soluções ambientais e sustentáveis. |
| 06 | Orçamentista | Estimativa e controle de custos. |
| 07 | Analista de Viabilidade Urbana | Análise do terreno e contexto urbano. |
| 08 | Agente de Apresentação | Organização e apresentação dos resultados. |

## 🛠️ Tecnologias utilizadas

| Tecnologia | Aplicação |
|---|---|
| n8n | Automação e integração dos agentes. |
| LM Studio | Execução local dos modelos de linguagem. |
| Gemma 3 4B Instruct | Modelo de IA utilizado nos testes. |
| Node.js | Ambiente de execução do n8n. |
| Git | Controle de versão. |
| GitHub | Versionamento e documentação do projeto. |

## 🧩 Arquitetura de funcionamento

O sistema foi planejado para funcionar com agentes especializados que podem operar em computadores diferentes.

O fluxo conceitual é:

1. O Orquestrador recebe uma demanda.
2. A tarefa é encaminhada ao agente responsável.
3. O agente processa as informações utilizando seu modelo de IA.
4. A resposta é devolvida ao Orquestrador.
5. As contribuições são organizadas para dar continuidade ao planejamento.

**Modelo de comunicação planejado:**

```text
                 ORQUESTRADOR
                       |
        +--------------+--------------+
        |              |              |
     Agente 02      Agente 03      Agente 04
     Arquiteto      Engenheiro       Mayra
        |              |              |
        +--------------+--------------+
                       |
             Demais agentes
                       |
              RESULTADO FINAL
```

> A arquitetura representa o funcionamento planejado. A comunicação automática entre todos os agentes depende da implementação e validação das integrações.

## 📁 Estrutura do repositório

Organização sugerida para os arquivos:

```text
smartbuild-agents/
│
├── agents/
│   ├── agent-01-orchestrator/
│   ├── agent-02-architect/
│   ├── agent-03-structural-engineer/
│   ├── agent-04-interior-designer/
│   ├── agent-05-sustainability/
│   ├── agent-06-budget-analyst/
│   ├── agent-07-urban-analyst/
│   └── agent-08-presenter/
│
├── docs/
│
├── README.md
└── .gitignore
```

*Os diretórios devem refletir a estrutura efetivamente criada pela equipe.*

## ⚙️ Requisitos

Para executar os agentes localmente:

- Windows, Linux ou macOS.
- Node.js.
- n8n.
- LM Studio.
- Modelo de linguagem compatível.
- Conexão com a internet quando necessária para comunicação entre computadores.

## 🚀 Configuração inicial

### 1. Clonar o repositório

```bash
git clone URL_DO_REPOSITORIO
```

### 2. Acessar a pasta

```bash
cd smartbuild-agents
```

### 3. Preparar o ambiente

- Instalar o Node.js.
- Instalar e iniciar o n8n.
- Instalar o LM Studio.
- Baixar o modelo de IA definido para o agente.

### 4. Configurar o modelo

- Abrir o LM Studio.
- Carregar o modelo.
- Iniciar o servidor de API local.
- Configurar a conexão no n8n.

### 5. Configurar o agente

- Criar ou importar o workflow.
- Configurar o prompt de sistema.
- Conectar o modelo ao nó AI Agent.
- Executar testes individuais.

## 👥 Equipe de desenvolvimento

**SmartBuild AI — Projeto acadêmico**

| Nº | Integrante |
|:---:|---|
| 01 | Barbara Ingrid Santos da Silva |
| 02 | Lucas Matos de Arruda Silva |
| 03 | Cauany Maria da Silva |
| 04 | Pedro Victor Andrade Palmeira |
| 05 | Eduardo Santos Alves Castro |
| 06 | Arthur Miguel Gomes do Espírito Santo |
| 07 | Carlos Eduardo da Silva Santos |

## 📊 Status do projeto

| Etapa | Status |
|---|---|
| Definição da proposta | Concluída |
| Definição dos agentes | Concluída |
| Configuração inicial do ambiente | Concluída |
| Desenvolvimento dos agentes | Em andamento |
| Testes individuais | Em andamento |
| Documentação | Em andamento |
| Integração entre agentes | Em desenvolvimento |
| Testes de comunicação distribuída | Pendente |
| Validação do sistema completo | Pendente |
| Apresentação final | Pendente |

*Atualize os status conforme o andamento real da equipe.*

## 🔐 Segurança e boas práticas

- Nunca publicar senhas, tokens ou chaves de API.
- Não armazenar credenciais nos arquivos do GitHub.
- Utilizar credenciais protegidas no n8n.
- Manter os prompts e documentos organizados.
- Registrar alterações importantes utilizando commits.
- Validar as respostas produzidas pelos agentes.

## 🎓 Contexto acadêmico

O SmartBuild AI possui finalidade acadêmica e experimental. As propostas geradas pelos agentes servem como apoio ao planejamento e não substituem a avaliação de profissionais habilitados em arquitetura, engenharia e demais áreas envolvidas.

---

<p align="center">
  <strong>SMARTBUILD AI</strong>
  <br/>
  Construindo ideias com inteligência artificial.
  <br/><br/>
  • 🏗️ Tecnologia • 🤖 Inovação
</p>
