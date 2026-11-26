# Integração e portabilidade

> Conteúdo transcrito da documentação técnica e funcional do Agente 07.

• Proteger o computador, o acesso ao n8n e os arquivos do workflow.
• Não compartilhar credenciais ou informações sensíveis em capturas e arquivos públicos.
A utilização de um modelo local reduz a necessidade de enviar dados do projeto a serviços externos de
IA, mas não elimina a necessidade de proteger o ambiente computacional.
16. INTEGRAÇÃO FUTURA COM O SMARTBUILD AI
O Agente 07 foi estruturado para funcionar de maneira independente, mas sua arquitetura permite
integração futura ao sistema SmartBuild AI. A entrada When Executed by Another Workflow foi mantida
para essa finalidade.
16.1. Fluxo futuro previsto
1. O Orquestrador recebe os dados gerais do empreendimento.
2. Identifica a necessidade de uma análise urbanística.
3. Chama o workflow do Agente 07.
4. Envia os dados necessários.
5. Recebe o parecer preliminar.
6. Incorpora as pendências à análise geral.
7. Encaminha as verificações aos responsáveis ou agentes correspondentes.
O Agente 07 deverá continuar responsável por sua área específica de atuação, sem assumir as
atribuições dos demais agentes.
A entrada interna entre workflows permite a chamada dentro de uma mesma instância n8n. Caso os agentes
estejam em computadores e redes diferentes, será necessário implementar um mecanismo de comunicação
acessível entre as instâncias, com autenticação, controle de acesso e tratamento de falhas.
17. EXPORTAÇÃO E PORTABILIDADE
O workflow foi desenvolvido de maneira independente para facilitar sua exportação e utilização em
outro computador.
17.1. Exportação do workflow
1. Abrir o workflow do Agente 07 no n8n.
2. Acessar o menu de opções do workflow.
3. Utilizar a opção de download ou exportação em JSON.
4. Salvar o arquivo em local seguro.
5. Transferir o arquivo para o computador de destino.
O arquivo JSON contém a estrutura do workflow, os nós e suas configurações exportáveis.
17.2. Preparação do computador de destino
• Node.js e npm.
• n8n.
• Ollama.
• Modelo qwen2.5:3b.
• Credencial do Ollama configurada no n8n de destino.
17.3. Reconﬁguração e importação
1. Instalar o Ollama para Windows e baixar o modelo qwen2.5:3b.

2. Confirmar que o serviço está em execução e verificar a API local na porta 11434.
3. Criar ou configurar a credencial no n8n, utilizando o endereço local correspondente ao novo
ambiente.
4. Importar o arquivo JSON no n8n de destino.
5. Conferir os nós e suas conexões e reconfigurar credenciais não preservadas.
6. Executar um teste pela entrada manual.
A exportação do JSON não transfere automaticamente o modelo, o servidor Ollama, as instalações do
Node.js e do n8n ou as credenciais. O endpoint 127.0.0.1 precisa ser revisto conforme o ambiente de
destino.
18. COMANDOS DE REFERÊNCIA PARA REINSTALAÇÃO
Os comandos abaixo representam uma referência de preparação de um novo ambiente Windows. Não
devem ser interpretados como registro de todos os comandos efetivamente utilizados na instalação
original.
Finalidade
Comando
Verificar Node.js
node --version
Verificar npm
npm --version
Verificar Ollama
ollama --version
Instalar n8n globalmente
npm install -g n8n
Instalar modelo no Ollama
ollama pull qwen2.5:3b
Listar modelos
ollama list
Iniciar n8n
n8n
A execução do n8n e a disponibilidade do serviço Ollama devem ser verificadas antes de testar o
workflow.
19. MELHORIAS RECOMENDADAS E PLANO DE
VALIDAÇÃO
Esta seção organiza melhorias que podem fortalecer o agente e sua integração. Os itens abaixo são
recomendações de evolução, não funcionalidades confirmadas na versão documentada.
Prioridade
Melhoria recomendada
Critério de conclusão
Alta
Definir contrato de entrada e saída
com o Orquestrador.
Campos e tipos acordados e testados.
Alta
Padronizar a resposta para integração.
Saída estruturada válida e interpretável pelo
workflow consumidor.
Alta
Confirmar e versionar o System
Message ativo.
Cópia do prompt instalado com data e versão.
Média
Validar dados essenciais.
Entradas incompletas geram pendências
explícitas.
Média
Ampliar cenários de teste.
Testes com dados ausentes, restrições e
conflitos.
