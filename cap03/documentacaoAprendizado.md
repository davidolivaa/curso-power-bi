# Resumo com o passo-a-passo do projeto

#### Verificar configurações
- conferir as configuraçoes do projeto atual e alterar para ingles americano no menu de opçao para configuraçoes regionais

#### Transformar dados e criar as relações
- transformar os dados com o power query e com o botao direito do mouse clicar na tabela e duplica-la
- repetir isso algumas vezes e em cada tabela nova mudar o nome e escolher as colunas que serao usadas no botao no menu de cima
- na parte esquerda do power query com o botao direito do mouse criar um novo grupo
- essse sera usado pra armazenar as tabelas criadas
- em seguida, na tabela original selecionar somente as colunas que faltam/nao foram usadas nas outras tabelas e as colunas principais das outras tabelas
- isso cria um relacionamento entre as tabelas de pk e fk
- aplicar e fechar o power query, finalizando as mudanças nos dados
- agora usaremos o menu de modelo, la o power bi ja identifica as tabelas e os relacionamentos
- porem pode ocorrer erros e ele nao consegue identificar corretamente todos, entao é imprtante verificar
- para detectar as outras relaçoes de forma manual
- no menu superior clicar em gerenciar relaçoes e tentar automaticamente, caso de errado tentar em novo
- selecione as tabelas para relacionar e as colunas entao escolha corretamente a cardinalidade ou o power bi nao permitira a açao
- nesse projeto nao sera possivel pois a tabela DIm_LOJAS possui muitas duplicatas
- isso aconteceu porque a tabela inicial possuia os dados por venda, ou seja cada linha da tabela era uma venda diferente
- entao as tabelas que criamos seguiu isso e na de lojas apareceram muitas duplicatas ja que cada loja teve diversas vendas
- para arrumar isso vamos em transformar dados novamente, selecionar a tabela com o problema e com o botao direito do mouse apertar em remover duplicatas
- entao repetir o processo na aba de modelos e depois no menu de gerenciar relaçoes
- entao repetir a operaçao de remover duplicatas no power query das outras tabelas, ja que as tabelas de dimensao devem ter dados unicos, com exceçao das tabelas que possuem algum campo com id unico, como a de produtos no exemplo desse projeto
- apos esses passos, montar o dashboard