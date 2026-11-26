# Dados de entrada e formato do resultado

> Conteúdo transcrito da documentação técnica e funcional do Agente 07.

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

12.1. Conteúdo esperado das seções
Seção
Finalidade
Identificação do projeto
Apresentar dados básicos do empreendimento e características
principais.
Resumo da análise urbanística
Sintetizar condições gerais e verificações necessárias.
Uso e ocupação do solo
Organizar consultas sobre zoneamento, taxa de ocupação, coeficiente
de aproveitamento, recuos, permeabilidade e gabarito.
Implantação e terreno
Apresentar questões relacionadas à área, topografia e distribuição da
edificação.
Acessibilidade e circulação
Identificar verificações sobre circulação horizontal e vertical, acessos e
estacionamento.
Infraestrutura pública
Organizar verificações sobre água, esgoto, energia, internet e serviços
públicos.
Licenciamento e
regulamentação
Identificar licenças, autorizações e normas que precisam ser
consultadas.
Riscos potenciais
Apontar situações que podem gerar dificuldades ou impedir a
implantação.
Checklist e pendências
Reunir providências necessárias para aprofundar a análise.
Encaminhamento ao
Orquestrador
Organizar pendências para o sistema responsável pela coordenação.
A saída descrita é textual. A opção Require Specific Output Format está desligada e a documentação
não comprova a adoção de um JSON de saída obrigatório.
13. TESTES E VALIDAÇÃO
O Agente 07 foi desenvolvido com possibilidade de execução independente. A entrada manual foi
utilizada para testar seu comportamento sem depender de outro workflow.
13.1. Objetivos dos testes
• Verificar se o AI Agent recebia corretamente os dados.
• Verificar se o modelo local respondia às instruções.
• Avaliar se o System Message orientava adequadamente a análise.
• Conferir se a saída apresentava as dez seções previstas.
• Verificar se parâmetros urbanísticos eram apresentados como itens a consultar.
• Observar se o agente evitava inventar índices e exigências legais.
• Conferir se as pendências eram organizadas para encaminhamento futuro.
13.2. Teste de entrada manual
When clicking 'Execute workflow'
↓
Edit Fields
↓
AI Agent
O Edit Fields permitiu inserir os dados do Centro Comunitário Conecta Verde e executar o agente
diretamente pelo editor do n8n.
