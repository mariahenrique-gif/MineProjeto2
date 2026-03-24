## 📖 Descrição do Sistema LojaGas

O **Sistema LojaGas** é um mini sistema desenvolvido em Java para gerenciar uma loja de gás.  
Ele permite controlar o **estoque de produtos**, registrar **vendas e compras**, acompanhar o **caixa da empresa** e realizar a **persistência dos dados em arquivo**.  

### Funcionalidades principais
- **Controle financeiro**: registrar receitas e despesas, exibir relatórios e resumo do caixa.  
- **Gestão de estoque**: adicionar produtos, atualizar quantidades e calcular o valor total em estoque.  
- **Registro de operações**: vendas e compras atualizam automaticamente o saldo e o estoque.  
- **Persistência**: salvar e carregar o estado do sistema em arquivo.  
- **Pesquisa de produtos**: localizar produtos por nome, com uso de Streams para filtragem.  
- **Tratamento de exceções**: classes específicas para saldo insuficiente, quantidade inválida e estoque insuficiente.  

### Estrutura do projeto
- **`SistemaLoja`** → Interface que define os métodos principais.  
- **`LojaGas`** → Classe que implementa a interface e concentra as funcionalidades.  
- **`Caixa`** → Responsável pelo controle financeiro.  
- **`Estoque`** → Representa cada produto armazenado.  
- **`SalvaArquivos`** → Responsável pela persistência em arquivo.  
- **Exceções** → `SaldoInsuficienteException`, `QuantidadeInvalidaException`, `EstoqueInsuficienteException`.  

## 🔎 Análise de Coesão e Acoplamento

### **Coesão**
O sistema apresenta **alta coesão**, pois cada classe possui uma responsabilidade única e bem delimitada:
- **`Caixa`**: concentra apenas o controle financeiro, cuidando de saldo, receitas e despesas.  
- **`Estoque`**: representa e manipula informações de produtos, como quantidade e preços.  
- **`SalvaArquivos`**: trata exclusivamente da persistência em arquivo, sem interferir na lógica de negócio.  
- **`LojaGas`**: atua como núcleo do sistema, implementando a interface `SistemaLoja` e coordenando as interações entre estoque, caixa e persistência.  
- **Exceções**: cada uma cobre um cenário específico de erro (saldo insuficiente, quantidade inválida, estoque insuficiente).  

Essa divisão clara de responsabilidades evita sobreposição de funções e facilita a manutenção, demonstrando **coesão elevada**.

---

### **Acoplamento**
O sistema foi projetado com **baixo acoplamento**, o que significa que as classes se relacionam de forma controlada e independente:
- `LojaGas` depende de `Caixa`, `Estoque` e `SalvaArquivos`, mas cada classe pode ser modificada ou estendida sem impactar fortemente as demais.  
- As exceções são utilizadas apenas quando necessário, sem criar dependências rígidas.  
- A interface `SistemaLoja` garante que outras implementações possam substituir `LojaGas` sem alterar o restante do sistema.  
- O uso de **Streams** em pesquisas reduz a necessidade de lógica complexa dentro da classe principal, mantendo o acoplamento baixo.  
Quer que eu também prepare uma versão **mais resumida** dessa análise para ficar enxuta no README, e deixar a versão detalhada em um relatório separado?
