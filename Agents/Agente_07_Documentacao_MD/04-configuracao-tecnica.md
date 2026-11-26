# Configuração do agente e ambiente técnico

> Conteúdo transcrito da documentação técnica e funcional do Agente 07.

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

7.1. Exemplo de dados para teste
{
"projeto": "Centro Comunitário Conecta Verde",
"localizacao": "Zona urbana consolidada, cenário fictício",
"tipo_empreendimento": "Centro comunitário",
"area_terreno_m2": 1000,
"area_construida_maxima_m2": 1200,
"pavimentos_maximos": 2,
"orcamento_maximo": 4500000,
"prazo_meses": 24,
"capacidade_usuarios": 250,
"clima": "Tropical quente",
"topografia": "Leve declive",
"programa": [
"Laboratório de informática para 30 computadores",
"Coworking",
"Laboratório maker",
"Auditório",
"Café",
"Espaços de convivência",
"Administração",
"Sanitários"
]
}
Esse JSON é um exemplo de organização dos dados, não uma declaração de que todos os campos sejam
obrigatórios ou de que o agente valide automaticamente cada campo.
8. AMBIENTE COMPUTACIONAL
O desenvolvimento e os testes foram realizados em um notebook com Windows, utilizando instalação
local do n8n e do Ollama.
8.1. Hardware
Componente
Especificação registrada
Processador
AMD Ryzen 3 7320U
Memória RAM instalada
8 GB
Memória RAM utilizável informada
5,74 GB
GPU
AMD Radeon 610M integrada
Armazenamento
SSD de 238 GB
Sistema operacional
Windows
As limitações de memória e processamento devem ser consideradas ao executar modelos locais,
especialmente quando outros programas estiverem abertos.

8.2. Ambiente de execução
Componente
Versão ou configuração
Sistema operacional
Windows
Terminal utilizado
CMD
Docker
Não utilizado
n8n
2.48.6
Node.js
24.22.3
npm
11.19.1
Ollama
0.40.18
O n8n foi instalado diretamente no ambiente Windows por meio do npm global, sem utilização de
contêiner Docker.
9. DOCUMENTAÇÃO DO OLLAMA
9.1. Função e versão
O Ollama executa modelos de inteligência artificial localmente e fornece o modelo de linguagem
utilizado pelo AI Agent do n8n. A versão registrada é 0.40.18, instalada por meio do instalador para
Windows.
9.2. Modelo utilizado
Característica
Informação
Modelo
Qwen 2.5 3B
Identificação no Ollama
qwen2.5:3b
Tamanho aproximado
1,9 GB
Quantização informada
Q4_K_M
Contexto informado
32.768 tokens
9.3. API local do Ollama
A interface local de comunicação utiliza a porta 11434. O endereço configurado na credencial do n8n é:
http://127.0.0.1:11434
Esse endereço foi testado e funcionou na configuração do nó Ollama Chat Model. A documentação
registra que localhost não funcionou na credencial utilizada, motivo pelo qual foi adotado 127.0.0.1.
9.4. Funcionamento e comandos de administração
O Ollama pode permanecer ativo como serviço ou processo em segundo plano. Não é necessário
manter aberta uma sessão interativa de ollama run para que o n8n utilize a API, desde que o serviço
esteja em execução.
Finalidade
Comando
Consultar versão
ollama --version
Consultar modelos instalados
ollama list

Finalidade
Comando
Baixar o modelo
ollama pull qwen2.5:3b
Executar em modo interativo
ollama run qwen2.5:3b
Consultar modelos pela API
curl.exe http://localhost:11434/api/tags
A documentação original confirma que o modelo está instalado e que os comandos de execução
interativa e consulta da API foram utilizados. O comando de download é apresentado como
procedimento padrão, não como confirmação de que tenha sido o comando originalmente executado.
9.5. Comunicação entre n8n e Ollama
1. O usuário inicia uma execução do workflow.
2. O AI Agent recebe os dados do empreendimento.
3. O AI Agent encaminha as instruções ao modelo conectado.
4. O nó Ollama Chat Model comunica-se com o servidor local.
5. O Ollama processa a solicitação utilizando o Qwen 2.5 3B.
6. A resposta retorna ao AI Agent.
7. O AI Agent apresenta o resultado da análise.
10. DOCUMENTAÇÃO DO N8N
10.1. Função e versões
O n8n é a plataforma utilizada para criar, organizar e executar os workflows do SmartBuild AI. No
projeto, conecta os componentes, organiza as entradas, executa o AI Agent e permite a integração
futura entre agentes.
Componente
Versão
n8n
2.48.6
Node.js
24.22.3
npm
11.19.1
10.2. Instalação e caminho registrado
O n8n foi instalado globalmente por meio do npm no ambiente Windows. O caminho registrado para a
instalação global do npm é:
C:\Users\note9\AppData\Local\Author Software\nvm\installs\v24.22.3
Esse caminho corresponde ao ambiente de instalação global do npm utilizado.

10.3. Comandos de consulta e execução
Finalidade
Comando
Verificar Node.js
node --version
Verificar npm
npm --version
Verificar n8n
n8n --version
Listar pacotes globais
npm list -g --depth=0
Iniciar n8n
n8n
Os comandos são referências para consulta e operação do ambiente; não representam
necessariamente uma sequência integral executada durante a instalação original.
11. CONFIGURAÇÃO DA CREDENCIAL OLLAMA NO N8N
A conexão entre o n8n e o Ollama utiliza uma credencial configurada no nó Ollama Chat Model.
Campo
Valor registrado
Tipo de conexão
Ollama
Base URL
http://127.0.0.1:11434
Modelo
qwen2.5:3b
Temperature
0.1
A temperatura baixa foi utilizada para favorecer respostas mais consistentes e reduzir variações
desnecessárias na análise. O nó Ollama Chat Model deve estar conectado à entrada Chat Model do AI
Agent.
12. FORMATO DO RESULTADO DO AGENTE
A saída do Agente 07 foi orientada para produzir um parecer preliminar dividido em dez seções.
1. Identificação do projeto.
2. Resumo da análise urbanística.
3. Uso e ocupação do solo.
4. Implantação e características do terreno.
5. Acessibilidade e circulação.
6. Infraestrutura pública.
7. Licenciamento e regulamentação.
8. Riscos potenciais.
9. Checklist de verificações e pendências.
10. Encaminhamento ao Orquestrador.
