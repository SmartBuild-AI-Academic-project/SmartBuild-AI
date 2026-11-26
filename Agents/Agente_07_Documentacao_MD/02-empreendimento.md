# Empreendimento de referência

> Conteúdo transcrito da documentação técnica e funcional do Agente 07.

• Não calcula parâmetros que dependam de informações ausentes.
• Não declara que o empreendimento está legalmente aprovado nem garante a obtenção de licenças.
• Não substitui consultas à legislação municipal e aos órgãos competentes.
• Não emite aprovação técnica ou jurídica definitiva.
A análise possui caráter preliminar e orientativo. O agente não substitui consultas aos órgãos públicos,
análise jurídica, aprovação de projetos ou responsabilidade técnica de profissionais habilitados.
4. IDENTIFICAÇÃO DO EMPREENDIMENTO
O agente foi desenvolvido e testado utilizando como referência o empreendimento acadêmico Centro
Comunitário Conecta Verde.
4.1. Dados gerais
Informação
Dados do projeto
Nome
Centro Comunitário Conecta Verde
Tipo de empreendimento
Centro comunitário
Localização
Zona urbana consolidada — cenário fictício
Área do terreno
1.000 m²
Área construída máxima
1.200 m²
Número máximo de pavimentos
2
Orçamento máximo
R$ 4.500.000,00
Prazo estimado
24 meses
Capacidade
Até 250 usuários simultâneos
Condição climática
Tropical quente
Topografia
Leve declive
4.2. Programa de necessidades
• Laboratório de informática para 30 computadores.
• Espaço de coworking.
• Laboratório maker.
• Auditório.
• Café.
• Espaços de convivência.
• Área administrativa.
• Sanitários.
4.3. Limitação dos dados do empreendimento
O cenário utilizado é acadêmico e fictício. Não foram fornecidos dados documentais suficientes para
confirmar:
• Endereço e identificação cadastral do terreno ou matrícula imobiliária.
• Zoneamento municipal específico e parâmetros urbanísticos oficiais.
• Levantamento topográfico detalhado.

• Condições reais das redes de infraestrutura.
• Restrições ambientais ou patrimoniais.
• Exigências específicas dos órgãos licenciadores.
Por esse motivo, o agente trabalha com verificações necessárias, sem afirmar conformidade legal.
5. ARQUITETURA DO WORKFLOW NO N8N
O Agente 07 foi construído como um workflow independente no n8n. Sua arquitetura possui duas
entradas distintas, que convergem para o mesmo nó de inteligência artificial.
5.1. Estrutura geral
Entrada para integração futura:
When Executed by Another Workflow
↓
AI Agent
↑
Ollama Chat Model
Entrada para testes independentes:
When clicking 'Execute workflow'
↓
Edit Fields
↓
AI Agent
As duas entradas utilizam o mesmo agente e o mesmo modelo de linguagem.
5.2. Nó: When Executed by Another Workflow
Responsável por permitir que o Agente 07 seja chamado por outro workflow do n8n e receber os dados
enviados pelo workflow responsável pela chamada. A utilização prevista é a execução automatizada
pelo Orquestrador ou por outro agente responsável pela coordenação.
5.3. Nó: When clicking 'Execute workflow'
Permite executar manualmente o workflow pelo editor do n8n. Foi utilizado para testar o agente de
forma independente, sem depender de outro workflow para fornecer os dados.
5.4. Nó: Edit Fields
Conectado à entrada manual, permite inserir, editar e organizar os dados encaminhados ao agente
durante os testes. Funciona como mecanismo de preparação dos dados e não realiza a análise de
viabilidade urbana.
5.5. Nó: AI Agent
É o componente central do workflow. Recebe os dados, interpreta as informações do empreendimento,
aplica as instruções do System Message, utiliza o modelo conectado e produz o parecer preliminar com
riscos e pendências.
5.6. Nó: Ollama Chat Model
Fornece o modelo de linguagem utilizado pelo AI Agent e estabelece a comunicação entre o n8n e o
servidor local do Ollama. O modelo configurado é qwen2.5:3b.
