# Resumo com o passo-a-passo do projeto

#### Verificar configurações
- conferir as configuraçoes do projeto atual e alterar para ingles americano no menu de opçao para configuraçoes regionais

#### Transformar dados e criar as relações
- logo no inicio percebemos que os nomes das colunas de algumas tabelas esta generico, isso atrapalha muito a identificaçao do significado ao criar os graficos
- para concertar vamos em **transformar dados** e no menu superior do power query em **usar primeira linha como cabeçalho**
- repetir esse processo em todas as tabelas e fechar e aplicar as mudanças
- verificar relacionamentos da tabela, ja que alguns graficos nao sao possiveis criar nesse exemplo pois as tabelas nao se relacionam (isso aconteceu porque nesse exercicio as tabelas/planilhas vieram separadas, diferente do capitulo anterior que todos os dados vieram na mesma tabela facilitando por power bi identificar as relaçoes) 
- para entender melhor a cardinalidade e o tipo de relacionameto muitos para muitos, vamos carregar uma nova base de dados, as planilhas do arquivo produtos, e criar um **projeto 2**
- no painel de relacionamento, clicar em **gerenciar relacionamento e depois em novo**
- o programa automaticamente ja identifica o relacionamento muitos para muitos
- entao o power bi emite um aviso sobre como pode ser perigoso criar esse tipo de ralaçao sem conhece-la direito
- nesse caso usaremos uma tabela intermediaria(tabela de tipo de produtos) como um meio mais seguro de criar esse relacionamento
- antes devemos ainda no painel de relacionamentos clicar em transformar dados ja que novamente os nomes das colunas esta generico
- apos esse passo, o power bi consegue identificar os relacionamentos entre as 3 tabelas que antes nao havia conseguido
- no entanto, deve se verificar se esta correto
- para editar as propriedade dos relacionamentos, podemos clicar duas vezes nas linhas que conectam as tabelas ou usar o botao direito do mouse
- agora vamos deixar a cardinalidade de muitos para 1, mas vamos ativar o filtro cruzado na tabela do meio(tipo produto) e colocar a opçao ambas
- isso vai fazer a direçao do relacionamento ser em ambos os sentidos, criando uma seta a mais na linha que conecta as tabelas
- o filtro cruzado faz com que a tabela intermediaria nao tenha valores duplicados
- agora o grafico esta coerente
- voltando ao projeto 1 vamos na aba de relacionamentos e excluir os que tiver para poder cria-los manualmente
- antes vamos tentar fazer alguns graficos para ver que sem os relacionamentos nao é possivel, no painel de graficos mesmo quando uma mensagem de erro aparece ao tentar criar um grafico, clicando em resolver o erro é possivel criar manualmente os relacionamentos
- faremos primeiro o relacionamento entre produtos e vendas, ao selecionar as tabelas o power bi ja identifica um relacionamento mas com cardinalidade 1 para 1, que esta errada
- nesse caso usaremos o filtro cruzado em sentido unico

##### Projeto 3
- vamos aprender Power M e DAX
- carregar a base dados 'Custos.csv'
- ir para o **Power Query** atraves do botao transformar dados
- vamos juntas duas colunas, Produto e Serial Number com Power M
- para isso precisamos que a barra de formulas apareça, clicando em **exibição** no menu superior e depois habilitando a **barra de ferramentas** clicando no check
- depois clicar em **adicionar coluna** no menu superior
e ir na opçao **coluna personalizada**, nela clicar duas vezes nas colunas indicadas e entre elas adicionar um '&', depois renomear a nova coluna
- clicar em **fechar e aplicar**
- agora vamos fazer um processo parecido mas com DAX
- no painel de dados, na aba de ferramenta de tabela, clicar em nova coluna
- a coluna é criada vazia
- vamos entao na barra de tarefas e escrever o código para preenche-la
- basta abrir [] e entao colocar o nome das colunas com & entre elas
- usando uma terceira forma de juntar colunas mas tambem com DAX é usar formulas, basta clicar em nova coluna novamente mas na barra de tarefas escrever a funçao Concatenate
- agora que sabemos juntar colunas de diferentes formas podemos apagar as utimas duas ja que as 3 sao iguais
- criada a coluna, renomear para margem de lucro e usar a funçao DIVIDE e como parametros colocar preço de custo e valor de venda, alem de um 0 caso ocorra algum erro na divisao esse numero é exibido
- entao selecionando a coluna ir no botao de formato e alterar pra porentagem
- agora vamos criar uma medida, existem varios tipos e vamos criar uma media, nao sera criada nenhuma coluna nova ja que a media é apenas um valor, entao ela sera inserida no menu de Campos no lado direito do painel
- para criar a medida, precisamos ir na aba de **ferramentas da tabela** e clicar em **nova medida**
- vamos renomear a medida para media_vendas e entao na barra de ferramentas inserir a funçao average e enviar a coluna de vendas como parametro
- entao na area de relatorio criar umgrafico de barras usando o item de media de vendas criado e os produtos
- Em seguida resolver o exercicio proposto criando o dashboard