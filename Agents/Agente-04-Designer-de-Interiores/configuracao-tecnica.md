# Configuração técnica — LM Studio + n8n

## Ambiente registrado

| Componente | Configuração conhecida |
|---|---|
| Sistema operacional | Windows |
| Modelo | Gemma 3 4B Instruct |
| Executor local | LM Studio |
| Endpoint OpenAI-compatible | `http://127.0.0.1:1234/v1` |
| Orquestração | n8n self-hosted |
| n8n | 2.35.7 |
| Node.js | v22.23.5 |

## Inicialização local

1. Abrir o LM Studio.
2. Carregar o modelo Gemma 3 4B Instruct.
3. Iniciar o servidor local de API no LM Studio.
4. Confirmar que o endpoint configurado está disponível.
5. Abrir o CMD e iniciar o n8n conforme a instalação local.
6. Acessar `http://localhost:5678`.
7. Abrir o workflow e executar um teste com o AI Agent.

## Configuração do modelo

O endpoint registrado durante a configuração foi:

```text
http://127.0.0.1:1234/v1
```

O endereço é local à máquina em que LM Studio e n8n estão sendo executados. Se os serviços estiverem em ambientes diferentes, `127.0.0.1` pode apontar para o próprio ambiente do n8n, e não para o computador host. Nesse caso, a rede e o endereço de acesso precisam ser ajustados.

## System Message

O prompt de sistema da Mayra deve ser inserido no campo apropriado do AI Agent ou da configuração equivalente utilizada no workflow. A versão consolidada sugerida está em `prompt-sistema.md`.

Antes de substituir o prompt atual:
- Compare a versão instalada com a versão documentada.
- Preserve uma cópia da versão anterior.
- Faça um teste simples de identidade e limites.
- Registre a data e a mudança realizada.

## Estado da integração multidisciplinar

Os testes comportamentais foram realizados com mensagens fornecidas à Mayra, inclusive mensagens atribuídas a outros agentes. Até que existam workflows que encaminhem mensagens entre os agentes, essas interações devem ser descritas como simulações manuais.

Não declarar que existe comunicação autônoma entre os oito agentes apenas porque os prompts foram testados individualmente.

## Evidências técnicas recomendadas

- Captura da configuração do servidor LM Studio (sem expor chaves ou dados sensíveis).
- Captura do modelo carregado.
- Captura da configuração do AI Agent no n8n.
- Execução bem-sucedida de uma entrada e saída.
- Exportação do workflow, se permitido pelo projeto.
- Registro de versão do prompt utilizado.
