# Avaliação — Engenharia de Software
**Sistema Integrado de Gestão de Farmácia — MVP Definido pelo Estudante**

Aluno: *Pollyana Caso*  
RA: *25001334*  
Data: *25/03/2026*  

---

# 1. Definição do MVP
Meu MVP é sobre vendas dentro de uma farmácia, desde a identificação ou cadastro de um cliente até o final da compra e a emissão da nota fiscal. 

Dentro dele existe funcionalidades mais computacionais como relatorios com dados de fornecedores para controle financeiro no final do mês, mas ainda sim que de pra acompanhar o dia a dia do sistema da farmácia. Ficaram de fora as funcionalidades como a gestão financeira completa e detalhada, contas a pagar e os indicadores de desempenho justamente para manter o foco o funcionamento basico do sistema.

Escolhi isso por que a venda é a parte mais crítica do sistema e que impacta diretamente no funcionamento da farmácia.

---

# 2. Regras de Negócio (mínimo: 5)
Liste e descreva **cada RN** de forma clara.

**RN01 — O sistema não pode vender se não tiver o produto no estoque**  
**RN02 — Cada venda tem que ser atualizada o estoque do produto que foi vendido**  
**RN03 — As vendas a prazo ou "fiadas" tem que gerar automaticamente uma conta a receber**  
**RN04 — Apenas farmaceuticos podem atorizar e assinar vender medicamentos com prescrição médica** 
**RN05 — Clientes que não existam no sistema podem ser cadastrados no momento da venda**  

---

# 3. Requisitos Funcionais (mínimo: 8)
Liste os requisitos funcionais do seu MVP.

**RF01 — O sistema deve permitir consultar produtos por nome, código ou fabricante**  
**RF02 — O sistema deve permitir cadastrar um novo cliente**  
**RF03 — O sistema deve registrar a venda**  
**RF04 — O sistema deve verificar o estoque antes de finalizar a venda**  
**RF05 — O sistema deve atualizar o estoque depois de cada venda finalizada**  
**RF06 — O sistema deve emitir nota fiscal e salvar a nota**  
**RF07 — O sistema deve permitir que apenas farmaceuticos autorizem venda de medicamentos de prescrição médica**  
**RF08 — O sistema deve permitir vendas a prazo e automaticamente após essa venda gerar contas a receber**  

---

# 🛡 4. Requisitos Não Funcionais (mínimo: 4)
Liste os RNFs do sistema conforme seu MVP.

**RNF01 — O sistema deve ter uma interface simples**  
**RNF02 — O sistema deve responder rapidamente as consultas de produtos**  
**RNF03 — O sistema deve deixar armazenado todas as notas fiscais emitidas no formato XML por no mínimo 5 anos**  
**RNF04 — O sistema deve possuir segurança no acesso com login e senha**  
**RNF04 — O sistema deve estar disponivel o tempo todo durante o funcionamento da famrmacia**

---

# 5. Casos de Uso (mínimo: 10)
### Inserir **diagrama de casos de uso geral**, demonstrando claramente:
- os 10 casos
- relação entre eles e atores
- pelo menos 3 includes
- pelo menos 3 extends

---

# 6. Documentação dos Casos de Uso

## **UC01 - Realizar Venda**
**Ator(es): Atendente e/ou farmaceutico**  
**Descrição: Serve para registrar a venda de produtos para um cliente no sistema.**  
**Pré-condições:**  
**Pós-condições:**  

### Fluxo Principal
1.  
2.  
3.  
4.  

### Fluxos Alternativos / Exceções
- FA01 —  
- FA02 —  

### Relacionamentos
- **Include:** (listar quando aplicável)  
- **Extend:** (listar quando aplicável)  

### Inserir o diagrama de atividades do Caso de Uso, demonstrando tudo o fluxo princial e alternativos/exceções.

---

> Repita essa estrutura para **todos os seus casos de uso** (mínimo 10).



