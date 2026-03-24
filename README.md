# 🛒 Sistema de Gestão de Loja de Gás

Este projeto é um **mini sistema em Java** para gerenciar uma loja de gás, permitindo controle de estoque, vendas, compras e finanças. Ele utiliza coleções (`Map`) para armazenar os produtos e oferece persistência simples em arquivos de texto.

---

## ✨ Funcionalidades

- **Financeiro**
  - Registrar gastos com validação de saldo
  - Exibir relatório financeiro com receitas e despesas

- **Estoque**
  - Adicionar produtos
  - Registrar vendas e compras
  - Pesquisar produtos por nome
  - Exibir estoque ordenado

- **Persistência**
  - Salvar estado do sistema em arquivo
  - Carregar registros salvos

---

## 🧩 Estrutura de Classes

- `LojaGas`: Classe principal que implementa `SistemaLoja`
- `Caixa`: Gerencia saldo, receitas e despesas
- `Estoque`: Representa um produto
- `SalvaArquivos`: Salva e carrega dados em arquivo
- `SistemaLoja`: Interface com os métodos do sistema
- `TesteLojaGas`: Classe de testes com cadastro, pesquisa e remoção de produtos

---

## 📊 Análise de Coesão e Acoplamento

### 🔹 Coesão
- **LojaGas**: Alta coesão, pois concentra apenas as operações da loja (estoque, vendas, compras e finanças).  
- **Caixa**: Alta coesão, responsável apenas pelo controle financeiro (saldo, receitas e despesas).  
- **Estoque**: Alta coesão, representa exclusivamente um produto e suas informações.  
- **SalvaArquivos**: Alta coesão, responsável apenas pela persistência em arquivos.  

➡️ Cada classe tem uma **responsabilidade única e bem definida**, o que aumenta a clareza e facilita a manutenção.

### 🔹 Acoplamento
- **LojaGas** depende de `Caixa`, `Estoque` e `SalvaArquivos`.  
- O acoplamento é **moderado**, pois `LojaGas` precisa interagir diretamente com essas classes para executar suas funções.  
- O uso de uma **interface (`SistemaLoja`)** reduz o acoplamento externo, permitindo que outras implementações possam substituir `LojaGas` sem alterar o restante do sistema.  

➡️ O sistema apresenta **alta coesão e baixo a moderado acoplamento**.
---

## 📌 Observações

- Os dados são salvos em arquivos de texto simples.
- O sistema não utiliza banco de dados.
- A classe de testes (`TesteLojaGas`) demonstra cadastro, pesquisa e remoção de produtos no `Map`.

---

Maria, você gostaria que eu também escrevesse o **código da classe `TesteLojaGas`** com exemplos práticos de cadastro, pesquisa e remoção para deixar o projeto pronto para rodar?
