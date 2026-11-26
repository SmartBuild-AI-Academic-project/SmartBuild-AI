# Arquitetura do workflow no n8n

> Conteúdo transcrito da documentação técnica e funcional do Agente 07.

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

6. CONFIGURAÇÕES DO AI AGENT
Parâmetro
Configuração registrada
Nó
AI Agent
Tipo de entrada
User Message
Origem dos dados
JSON recebido pelo workflow
System Message
Fixed
Max Iterations
3
Require Specific Output Format
Desligado
Modelo conectado
Ollama Chat Model
6.1. User Message
O campo User Message utiliza a expressão abaixo para transformar os dados recebidos em uma
representação JSON formatada:
{{ JSON.stringify($json, null, 2) }}
A mesma expressão funciona para dados enviados por outro workflow e para dados preparados
manualmente pelo Edit Fields.
6.2. System Message
O System Message define o comportamento, as responsabilidades e as limitações do agente. Conforme
a documentação original, contempla identificação do empreendimento, orientações de análise
urbanística, uso e ocupação do solo, implantação e características do terreno, acessibilidade,
infraestrutura, licenciamento, riscos, checklist e encaminhamento ao Orquestrador.
Também estabelece restrições para evitar a criação de informações legais, índices urbanísticos ou
dados técnicos que não tenham sido fornecidos.
6.3. Max Iterations e formato de saída
O parâmetro Max Iterations está configurado em 3. A opção Require Specific Output Format permanece
desligada; portanto, a saída é organizada pelas instruções textuais do System Message, sem formato
estruturado obrigatório configurado por esse recurso.
7. MODELO DE DADOS DE ENTRADA
O agente recebe informações em formato JSON. Os campos podem representar identificação do
projeto, localização, tipo de empreendimento, áreas, número de pavimentos, orçamento, prazo,
capacidade de usuários, características do terreno, programa de necessidades e informações
complementares.
