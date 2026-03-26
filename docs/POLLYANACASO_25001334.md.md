# Avaliação — Engenharia de Software
**Sistema Integrado de Gestão de Farmácia — MVP de vendas dentro de uma farmácia**

Aluno: *Pollyana Caso*  
RA: *25001334*  
Data: *25/03/2026*  

---

# 1. Definição do MVP
Meu MVP é sobre vendas dentro de uma farmácia, desde a identificação ou cadastro de um cliente até o final da compra e a emissão da nota fiscal. 

Dentro dele existe funcionalidades mais complicadas como relatorios com dados de fornecedores para controle financeiro no final do mês, mas ainda sim que de pra acompanhar o dia a dia do sistema da farmácia. Ficaram de fora as funcionalidades como a gestão financeira completa e detalhada, contas a pagar e os indicadores de desempenho justamente para manter o foco o funcionamento basico do sistema.

Escolhi isso por que a venda é a parte mais crucial do sistema e impacta diretamente no funcionamento da farmácia.

---

# 2. Regras de Negócio 

**RN01 — O sistema não pode vender se não tiver o produto no estoque**  
- O sistema nao deve permitir a venda de produtos que nao tenham quantidade disponivel no estoque. 
**RN02 — Cada venda tem que ser atualizada o estoque do produto que foi vendido**  
- Sempre que uma venda for finalizada, o sistema deve atualizar automaticamente a quantidade do produto no estoque  
**RN03 — As vendas a prazo ou "fiadas" precisam ser geradas no sistema uma conta a receber**  
- Quando a venda for feita a prazo, o sistema tem que gerar automaticamente uma conta a receber com as informações   da venda  
**RN04 — Apenas farmaceuticos podem atorizar e assinar vender medicamentos com prescrição médica**  
- A venda de medicamentos que exigem receita médica só pode ser realizada com a autorização de um farmacêutico  
 **RN05 — Clientes que não existam no sistema podem ser cadastrados no momento da venda**    
- Caso o cliente não esteja cadastrado, o sistema tem que permitir a entrada desse novo cliente no momento da venda  
---

# 3. Requisitos Funcionais 

**RF01 — O sistema permite consultar produtos por nome, código ou fabricante**  
**RF02 — O sistema permite cadastrar um novo cliente**  
**RF03 — O sistema registra a venda**  
**RF04 — O sistema verifica o estoque antes de finalizar a venda**  
**RF05 — O sistema atualiza o estoque depois de cada venda finalizada**  
**RF06 — O sistema emite nota fiscal e salvar a nota**  
**RF07 — O sistema permite que apenas farmaceuticos autorizem venda de medicamentos de prescrição médica**  
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

## **UC05 - Autorizar venda controlada**
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

## **UC06 - Registrar Pagamento**
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

## **UC07 - Gerar conta a receber**
**Ator(es): Sistema**  
**Descrição: serve para registrar as vendas a prazo**  
**Pré-condições: Venda a prazo realizada**  
**Pós-condições: Conta registrada**  

### Fluxo Principal
1.  O sistema identifica que tem uma venda a prazo
2.  Cria uma conta a receber
3.  Define quando ela vai vencer

### Fluxos Alternativos / Exceções
- FA01 —  Se tem erro no registro - sistema tem que tentar novamente

### Relacionamentos
- **Include: -**
- **Extend: -**                      

<img width="248" height="312" alt="image" src="https://github.com/user-attachments/assets/c2e00335-c61b-4439-a88d-3476013b3adc" />

---

## **UC08 - Emitir o comprovante**
**Ator(es): Sistema**  
**Descrição: Gera o comprovante da venda**  
**Pré-condições: Venda finalizada**  
**Pós-condições: Comprovante emitido**  

### Fluxo Principal
1.  Sistema pega os dados da venda 
2.  Gera o comprovante
3.  exibe na tela ou imprime

### Fluxos Alternativos / Exceções
- FA01 —  erro na emissão - sistema tem que tentar novamente 

### Relacionamentos
- **Include: -**
- **Extend: -**                      

<img width="330" height="327" alt="image" src="https://github.com/user-attachments/assets/982ebe21-a8ad-4fc1-a6b9-d0ed15fa5bb9" />

---

## **UC09 - Atualizar o estoque**
**Ator(es): Sistema**  
**Descrição: Dá baixa nos produtos vendidos**  
**Pré-condições: Venda estar concluida**  
**Pós-condições: Estoque estar atualizado**  

### Fluxo Principal
1.  O sistema identifica os produtos vendidos
2.  Atualiza a quantidade 
3.  Salva as alterações

### Fluxos Alternativos / Exceções
- FA01 — Se der erro no estoque - o sistema registra falha 
- FA02 —  

### Relacionamentos
- **Include: -**
- **Extend: -**
                       
<img width="227" height="312" alt="image" src="https://github.com/user-attachments/assets/0c657a8a-8b18-4b73-b9ac-1ad2bf4b61ea" />

---

## **UC10 - Cancelar a venda**
**Ator(es): Atendente**  
**Descrição: Cancela uma venda que foi registrada incorretamente**  
**Pré-condições: Venda já registrada no sistema**  
**Pós-condições: Venda cancelada e estoque arrumado**  

### Fluxo Principal
1.  O atendente solicita o cancelamento no sistema
2.  Informa qual venda foi
3.  Sistema localiza a venda
4.  Sistema valida se pode cancelar
5.  Atendente confirma o cancelamento
6.  Sistema cancela a venda
7.  Sistema devolve o produto no estoque

### Fluxos Alternativos / Exceções
- FA01 — A venda nao ser encontrada - sistema informa o erro  
- FA02 —  Venda já ter sido feita a muito tempo - sistema bloqueia pra cancelar 

### Relacionamentos
- **Include: Atualizar o estoque**
- **Extend: -**
                  
<img width="464" height="486" alt="image" src="https://github.com/user-attachments/assets/cd39c2de-88cf-4e9c-b465-bf1db7dadc58" />

---

