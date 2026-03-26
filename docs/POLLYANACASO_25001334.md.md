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

# 2. Regras de Negócio 
Liste e descreva **cada RN** de forma clara.

**RN01 — O sistema não pode vender se não tiver o produto no estoque**  
**RN02 — Cada venda tem que ser atualizada o estoque do produto que foi vendido**  
**RN03 — As vendas a prazo ou "fiadas" tem que gerar automaticamente uma conta a receber**  
**RN04 — Apenas farmaceuticos podem atorizar e assinar vender medicamentos com prescrição médica** 
**RN05 — Clientes que não existam no sistema podem ser cadastrados no momento da venda**  

---

# 3. Requisitos Funcionais 

**RF01 — O sistema deve permitir consultar produtos por nome, código ou fabricante**  
**RF02 — O sistema deve permitir cadastrar um novo cliente**  
**RF03 — O sistema deve registrar a venda**  
**RF04 — O sistema deve verificar o estoque antes de finalizar a venda**  
**RF05 — O sistema deve atualizar o estoque depois de cada venda finalizada**  
**RF06 — O sistema deve emitir nota fiscal e salvar a nota**  
**RF07 — O sistema deve permitir que apenas farmaceuticos autorizem venda de medicamentos de prescrição médica**  
**RF08 — O sistema deve permitir vendas a prazo e automaticamente após essa venda gerar contas a receber**  

---

# 4. Requisitos Não Funcionais

**RNF01 — O sistema deve ter uma interface simples**  
**RNF02 — O sistema deve responder rapidamente as consultas de produtos**  
**RNF03 — O sistema deve deixar armazenado todas as notas fiscais emitidas no formato XML por no mínimo 5 anos**  
**RNF04 — O sistema deve possuir segurança no acesso com login e senha**  
**RNF04 — O sistema deve estar disponivel o tempo todo durante o funcionamento da famrmacia**

---

# 5. Casos de Uso 
<img width="531" height="484" alt="image" src="https://github.com/user-attachments/assets/aa131a64-2ec2-4468-a41e-426d2bb628cf" />

---

# 6. Documentação dos Casos de Uso

## **UC01 - Realizar Venda**
**Ator(es): Atendente**  
**Descrição: Serve para registrar a venda de produtos para um cliente no sistema.**  
**Pré-condições: Produto cadastradi e sistema funcionando**  
**Pós-condições: venda registrada e estoque atualizado**  

### Fluxo Principal
1.  Atendente inicia a venda
2.  Sistema solicita o cliente
3.  Atendente informa ou busca o cliente
4.  Atendente adiciona os produtos
5.  Sistema verifica o estoque
6.  Atendente confirma a venda
7.  Sistema registra a venda
8.  Sistema atualiza o estoque
9.  Sistema emite o comprovante


### Fluxos Alternativos / Exceções
- FA01 —  Cliente não está cadastrado - sistema tem que permitir o cadastro
- FA02 —  Produto sem estoque - sistema não deixa continuar a venda

### Relacionamentos
- **Include: Consultar produto, verificar estoque, identificar cliente** 
- **Extend: Cadastrar cliente e gerar conta a receber** 

<img width="384" height="854" alt="image" src="https://github.com/user-attachments/assets/efd4b652-5845-4bad-9c08-c216cb7d80d0" />


---

## **UC02 - Identificar o cliente**
**Ator(es): Atendente**  
**Descrição: Serve para ver um cliente no sistema**  
**Pré-condições: Cliente cadastrado**  
**Pós-condições: Cliente vinculado a venda**  

### Fluxo Principal
1. Cliente informa CPF ou numero
2. Sistema busca o cliente
3. Sistema retorna os dados

### Fluxos Alternativos / Exceções
- FA01 —  Cliente não encontrado - pode cadastrar

### Relacionamentos
- **Include:**
- **Extend: Cadastrar cliente**
                      
<img width="269" height="312" alt="image" src="https://github.com/user-attachments/assets/24e8b572-294b-420d-85f9-65470bca2e2b" />

---

## **UC03 - Verificar estoque**
**Ator(es): Atendente**  
**Descrição: Serve para ver se tem produto disponivel**  
**Pré-condições: Produto selecionado**  
**Pós-condições: Quantidade informada**  

### Fluxo Principal
1.  Sistema recebe o produto 
2.  Consulta o estoque
3.  Mostra a quantidade disponivel

### Fluxos Alternativos / Exceções
- FA01 —  Se o produto nao tiver estoque - sistema informa indisponivel

### Relacionamentos
- **Include: -**
- **Extend: -**                      

<img width="297" height="312" alt="image" src="https://github.com/user-attachments/assets/7b0256a8-c876-4120-ac6b-8168e536e0d9" />

---

## **UC04 - Cadastrar Cliente**
**Ator(es): Atendente**  
**Descrição: Serve para cadastrar um novo cliente**  
**Pré-condições: Cliente não estar cadastrado**  
**Pós-condições: Cliente salvo no sistema**  

### Fluxo Principal
1.  Atendente abre o cadastro
2.  Preenche os dados
3.  Sistema valida as infos
4.  Sistema salva o cliente  

### Fluxos Alternativos / Exceções
- FA01 —  Se os dados estiverem invalidos - sistema pede correção

### Relacionamentos
- **Include: -**
- **Extend: -**                      

<img width="250" height="312" alt="image" src="https://github.com/user-attachments/assets/9e2e01d7-f4d4-43ce-b02b-2905dc9fa481" />

---

## **UC05 - Autorizar venda controlada **
**Ator(es): Farmaceutico**  
**Descrição: Serve pra liberar a venda de medicamentos controlados**  
**Pré-condições: Produto controlado selecionado**  
**Pós-condições: Venda autorizada**  

### Fluxo Principal
1.  Sistema identifica o medicamento controlado
2.  Solicita a autorização
3.  O farmaceutico valida a receita
4.  O sistema libera a venda

### Fluxos Alternativos / Exceções
- FA01 — Receita inválida - venda bloqueada 

### Relacionamentos
- **Include: -**
- **Extend: -**                      

<img width="312" height="257" alt="image" src="https://github.com/user-attachments/assets/c13e17b5-9ae0-4bc1-88e8-8dd1e0002cf4" />

---

## **UC06 Registrar Pagamento - **
**Ator(es): Atendente**  
**Descrição: Serve oara informar como o cliente vai pagar**  
**Pré-condições: A venda estar em andamento**  
**Pós-condições: Pagamento ser registrado**  

### Fluxo Principal
1. O atendente escolhe a forma de pagamento
2. O sistema registra se é a vista ou a prazo  

### Fluxos Alternativos / Exceções
- FA01 —  Se for a prazo - gera a conta   

### Relacionamentos
- **Include: -**
- **Extend: Gerar conta a receber**                      

<img width="318" height="257" alt="image" src="https://github.com/user-attachments/assets/6811e4d4-4488-4b55-ab7c-850ffb69e3d4" />

---




