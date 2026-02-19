# Base de Conhecimento

## Dados Utilizados

Descreva se usou os arquivos da pasta `data`, por exemplo:

| Arquivo | Formato | Utilização no Agente |
|---------|---------|---------------------|
| `historico_atendimento.csv` | CSV | Contextualizar interações anteriores |
| `perfil_investidor.json` | JSON | Personalizar recomendações |
| `produtos_financeiros.json` | JSON | Sugerir produtos adequados ao perfil |
| `transacoes.csv` | CSV | Analisar padrão de gastos do cliente |

> [!TIP]
> **Quer um dataset mais robusto?** Você pode utilizar datasets públicos do [Hugging Face](https://huggingface.co/datasets) relacionados a finanças, desde que sejam adequados ao contexto do desafio.

---

## Adaptações nos Dados

> Você modificou ou expandiu os dados mockados? Descreva aqui.

Os dados foram simplificados para o protótipo do agente.
Foram criados exemplos fictícios de clientes, perfis e transações com valores pequenos e categorias comuns (alimentação, transporte, lazer), apenas para demonstrar as funcionalidades do sistema.

Também foram adicionadas descrições curtas aos produtos financeiros para facilitar respostas rápidas do agente.

---

## Estratégia de Integração

### Como os dados são carregados?
> Descreva como seu agente acessa a base de conhecimento.

Os arquivos JSON e CSV são carregados no início da sessão do agente.
Os dados principais do cliente (perfil, saldo e transações recentes) são armazenados em memória e usados como contexto durante a conversa.

### Como os dados são usados no prompt?
> Os dados vão no system prompt? São consultados dinamicamente?

JSON: carregado como dicionário Python.

CSV: convertido em lista de registros ou DataFrame.

---

## Exemplo de Contexto Montado

> Mostre um exemplo de como os dados são formatados para o agente.

Dados do Cliente:

- Nome: João Silva
- Perfil: Moderado
- Saldo disponível: R$ 5.000

Últimas transações:

01/11: Supermercado – R$ 450
03/11: Streaming – R$ 55
05/11: Restaurante – R$ 120
08/11: Transporte – R$ 80

Produtos disponíveis:

- Conta digital sem tarifas
- Cartão de crédito com cashback
- CDB com rendimento de 100% do CDI
```
