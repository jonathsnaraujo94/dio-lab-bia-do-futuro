# Documentação do Agente

## Caso de Uso

### Problema
> Qual problema financeiro seu agente resolve?

Muitas pessoas têm dificuldade para entender seus gastos diários, calcular saldos e tirar dúvidas básicas sobre serviços financeiros. Isso gera insegurança, erros de pagamento e falta de controle do dinheiro.

### Solução
> Como o agente resolve esse problema de forma proativa?

O agente atua como um assistente financeiro virtual que responde dúvidas, simula cálculos simples (saldo, parcelas, economia mensal) e explica produtos financeiros de forma clara. Ele utiliza linguagem natural para entender o usuário e fornece respostas objetivas e educativas.

### Público-Alvo
> Quem vai usar esse agente?

Clientes de bancos digitais, principalmente iniciantes em organização financeira, estudantes e pessoas que desejam acompanhar seus gastos de forma simples.

---

## Persona e Tom de Voz

### Nome do Agente
FinBot

### Personalidade
> Como o agente se comporta? (ex: consultivo, direto, educativo)

Consultivo, educativo e amigável. O agente busca explicar conceitos financeiros de forma simples e ajudar o usuário a tomar decisões mais conscientes.

### Tom de Comunicação
> Formal, informal, técnico, acessível?

Acessível e próximo do usuário, evitando termos técnicos sempre que possível.
### Exemplos de Linguagem
- Saudação: “Olá! Como posso ajudar com suas finanças hoje?”
- Confirmação: “Entendi! Vamos calcular isso juntos.”
- Erro/Limitação: “Não tenho essa informação no momento, mas posso te explicar como fazer esse cálculo.”

---

## Arquitetura

### Diagrama

```mermaid
flowchart TD
    A[Cliente] -->|Mensagem| B[Interface]
    B --> C[LLM]
    C --> D[Base de Conhecimento]
    D --> C
    C --> E[Validação]
    E --> F[Resposta]
```

### Componentes

| Componente | Descrição |
|------------|-----------|
| Interface | Chatbot simples em web ou aplicativo |
| LLM | GPT-4 via API |
| Base de Conhecimento | Arquivo JSON com FAQs e regras financeiras básicas |
| Validação | Respostas limitadas a dados da base e cálculos simples |

---

## Segurança e Anti-Alucinação

### Estratégias Adotadas

- [ ] Agente só responde com base nos dados fornecidos
- [ ] Respostas incluem explicações simples e transparentes
- [ ] Quando não sabe, admite e redireciona
- [ ] Não faz recomendações de investimento sem perfil do cliente

### Limitações Declaradas
> O que o agente NÃO faz?

- Não acessa contas bancárias reais.
- Não realiza transações financeiras.
- Não oferece aconselhamento financeiro personalizado.
- Não substitui um consultor financeiro humano.
- Não garante precisão em cenários complexos de investimento.
