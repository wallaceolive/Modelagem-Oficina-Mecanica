# 🛠️ Modelagem Conceitual - Oficina Mecânica  

Este repositório contém o **Diagrama Entidade-Relacionamento (DER)** para um sistema de gerenciamento de ordens de serviço em uma oficina mecânica.  

## 📌 Visão Geral  
O objetivo é modelar um sistema capaz de gerenciar **clientes, veículos, ordens de serviço, mecânicos e peças** dentro de uma oficina.  

## 📜 Diagrama Entidade-Relacionamento (DER)  
![Diagrama da Oficina](diagrama-oficina.png)  

## 📊 Estrutura do Modelo  
### 🔹 Entidades e Relacionamentos  
- **Cliente** possui **um ou muitos veículos** (1:N).  
- **Veículo** pode ter **várias ordens de serviço** (1:N).  
- **Ordem de Serviço (OS)** é atribuída a **uma equipe de mecânicos** (N:1).  
- **Equipe** é composta por **múltiplos mecânicos** (N:M).  
- **Uma OS inclui vários serviços e peças** (N:M).  
- **Cada serviço tem um valor de mão de obra**, podendo estar numa **tabela de referência** (1:1).  

## 📌 Decisões de Modelagem Baseadas na Narrativa  
1. **Um cliente pode possuir múltiplos veículos.**  
2. **O valor da mão de obra pode estar na tabela Serviço ou em uma tabela separada.**  
3. **Os mecânicos participam de várias equipes ao longo do tempo.**  
4. **A OS tem um status detalhado para indicar sua fase no processo.**  
5. **Criamos uma tabela intermediária para armazenar as peças usadas em cada OS.**  
6. **O modelo mantém um histórico completo das OS e serviços realizados.**

## 📌 O diferencial desse modelo está na interpretação e enriquecimento da narrativa para garantir um sistema mais completo e funcional. Aqui estão os principais pontos que não foram especificados na narrativa, mas foram modelados com base na compreensão do contexto:

1. **Relacionamento Cliente - Veículo**
A narrativa apenas menciona que clientes levam veículos à oficina, mas não deixa claro se um cliente pode ter mais de um veículo.
**Adição:** Foi assumido que um cliente pode ter vários veículos (1:N), pois é comum que uma pessoa possua mais de um carro.
2. **Tabela de Referência de Mão de Obra**
A narrativa menciona que o valor da mão de obra vem de uma "tabela de referência", mas não especifica se essa tabela é separada ou se o valor está diretamente no serviço.
**Decisão:** Dependendo da necessidade do negócio, esse valor pode estar na própria tabela Serviço ou em uma tabela separada se houver uma padronização externa.
3. **Equipe de Mecânicos**
O texto menciona que uma equipe é responsável pelos serviços, mas não detalha a relação entre mecânicos e equipes.
**Adição:** Foi assumido que um mecânico pode participar de várias equipes ao longo do tempo (N:M).
4. **Status da Ordem de Serviço (OS)**
A narrativa menciona que uma OS tem um "status", mas não detalha quais são os possíveis estados.
**Adição:** Foi incluído um campo status na OS, assumindo que pode ter valores como "Aberta", "Em Andamento", "Aguardando Peças", "Concluída" e "Cancelada".
5. **Relacionamento Ordem de Serviço - Peças**
O texto apenas menciona que as peças são adicionadas à OS, mas não especifica quantidades.
**Adição:** Criamos uma tabela intermediária OS_Peça, permitindo registrar a quantidade de cada peça usada na ordem.
6. **Histórico de Serviços e Peças**
A narrativa sugere um modelo de controle, mas não menciona se há um histórico de serviços prestados.
**Adição:** Ao modelar as OS como entidades independentes (e não sobrescrevê-las), garantimos um histórico detalhado de cada serviço e peça utilizada em cada reparo.

## 📂 Estrutura do Repositório  
📁 `diagrama-oficina.png` → Imagem do DER  
📁 `README.md` → Documentação do projeto 

## 💻💡 Ferramenta

Para a modelagem do banco de dados, utilizei a ferramenta [draw.io (diagrams.net)](https://app.diagrams.net/), que permite criar diagramas de maneira intuitiva e integrada ao GitHub.

### 📍 Como abrir e editar o DER:

1. Acesse o arquivo `Modelo_Conceitual_Oficina.drawio` no repositório.
2. Se estiver no GitHub, clique em **"Open with"** e selecione **"diagrams.net"** (se disponível).
3. Caso queira editar localmente:
   - Baixe o arquivo `Modelo_Conceitual_Oficina.drawio`.
   - Acesse [draw.io](https://app.diagrams.net/).
   - Faça o upload do arquivo e edite conforme necessário.
     
## 📝 Autor  
**[Wallace Oliveira dos Santos]** - Desenvolvedor Fullstack e Modelador de Banco de Dados. 

