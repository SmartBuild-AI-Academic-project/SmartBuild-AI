# Testes, limitações e segurança

> Conteúdo transcrito da documentação técnica e funcional do Agente 07.

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

13.3. Teste de integração
A entrada When Executed by Another Workflow foi mantida para permitir a chamada do Agente 07 por
outro workflow. Essa entrada representa a estrutura de integração futura; o agente foi desenvolvido e
validado individualmente.
13.4. Resultado da validação
A última execução apresentou as dez seções previstas. O agente identificou parâmetros urbanísticos
relevantes e organizou verificações de infraestrutura, acessibilidade, licenciamento e implantação.
Também evitou apresentar índices urbanísticos específicos sem que esses dados tivessem sido
fornecidos.
Foram observadas afirmações conceituais otimistas sobre as condições do terreno e da infraestrutura
que não podem ser consideradas comprovações técnicas. O resultado deve ser interpretado como
parecer preliminar, e não como confirmação definitiva de viabilidade.
A documentação original considerou a versão testada suficiente para a entrega acadêmica, sem
necessidade de novas alterações na configuração do agente.
14. LIMITAÇÕES TÉCNICAS E FUNCIONAIS
14.1. Limitações do modelo
O Qwen 2.5 3B é um modelo relativamente pequeno, escolhido para permitir execução local no
hardware disponível. Seu desempenho pode variar conforme a complexidade da solicitação, o volume
de dados e as informações presentes no contexto. A resposta não deve ser considerada validação
técnica independente.
14.2. Limitações do ambiente computacional
O notebook possui 8 GB de RAM instalada, com 5,74 GB utilizáveis informados. A memória disponível e
o processador podem limitar a execução simultânea de aplicações e modelos maiores.
14.3. Limitações das informações urbanísticas
O cenário do empreendimento é fictício. Na configuração documentada, o agente não possui base
municipal de legislação integrada para confirmar automaticamente os parâmetros oficiais de uma
localidade. Suas respostas indicam o que deve ser verificado, mas não substituem a consulta à
legislação vigente.
14.4. Limitações da análise
• Não consulta automaticamente cadastros imobiliários.
• Não analisa matrícula imobiliária.
• Não realiza consulta oficial de zoneamento.
• Não aprova projetos nem emite licenças.
• Não calcula definitivamente índices urbanísticos.
• Não realiza análise jurídica nem assume responsabilidade técnica profissional.
15. SEGURANÇA, CONFIABILIDADE E
RESPONSABILIDADE
• Tratar informações não fornecidas como pendências, nunca como fatos confirmados.
• Não interpretar ausência de dados sobre zoneamento, legislação, infraestrutura ou documentação
como conformidade.
• Apresentar verificações necessárias e encaminhar pendências para análise posterior.

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
