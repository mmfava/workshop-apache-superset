---
created: 2025-03-03T12:18
updated: 2025-03-03T12:22
link: https://www.youtube.com/watch?v=_1_rg5gAAjE
title: Apache Superset | Open Source Data Exploration & Vizualization Platform
channel: elestio
---

# Transcrição

How to build data visualization dashboards for your database hi let's discover APA superset a free open source tool to transform your existing SQL databases into interactive charts and dashboards with ease during this video we will cover how to deploy your instance and connect your database then we will create data sets charts and dashboards as we already covered The Meta base on this channel we will highlight some pros and cons during the platform overview ready let's dive into the word of superset let's set up our instance of superset go to ls.io hit login you can see I already have an instance of postgrad that we will use later create a new service then search for superset select choose your cloud provider you can see now we also have scaleway available hit next choose your level of supports and hit create service we will receive an email as soon as our instance is deployed and ready okay I just received that email so I can go and click here to get the password that will lead me to the dashboard from here I can copy the password to my clipboard and go to my admin UI it will open superset this is what we get when we arrive for the first time the username is my email account on lso it automatically created by our process and the password is in my clipboard hit sign in but when you add other users they will be able to enter their credentials here when you arrive for the first time it's empty well you see you can have dashboards and shards but because we don't have yet we don't see them but it's good looking once you set up something the first thing we will need to do is to connect our database to superset to be able to create some database realization so let's go into it let's click on data sets here you can see we have already examples from server set but we want to connect our own database so data set oh it's when we already have it so here and connect database we can choose between all relational SQL database there are even a list here for other kind of database but keep in mind it's always SQL relational base mine is a pause Gray and all the information are on my post gray instance on LSU let's have a look at it here I open it and because it's a database I have the admin like all other services but I also have database admin and from here I will be able to find my information to connect into my database let's copy everything and connect now let's try to connect it's successfully connected it asks me either to create a data set what I tried earlier or to use Query data in SQL lab but we will see it later let's go to create data set now on the left before I had examples now I have post gray I select this one I select the schema mine is public and I just created two tables one is the sales and the other one is a user's table it's very simple data but it's to show you how to connect it and how to create charts from your own data we will start playing with users you see what are the column and data type it's what I want to use so create data set and create chart from here you can create different kind of charts the big number table charts line chart bar chart area chart you have multiple ways to do it and customize it let's say we want the number of new users per day maybe we will use a big number with trend line and create new chart here compared to metabase it's less user friendly so you have a lot of options it's very powerful but not so easy and intuitive it could be on metabase let's select the metric we want to display so it already has a saved metric but we want to use a simple one let's say we won't the column ID and the count distinct then we need to create the chart and here we have one user it displaying one which is the latest value but we had two new users here two new users on the 21st and on the 22nd only one so maybe big number is not the best choice we can we could use bar charts we need to change the x-axis let's use the created at date and hit update chart okay so here we have two new users two new users and one new user so you can see daily how many new users we have okay let's say we can create an another one new users per day save it and let's create another one you can see there are a lot of example maybe if you really start your own project delete them before starting working with your own so let's create another chart and let's use a line chart I also need to choose my data sets so it's in the users create new chart so on the x-axis it will be the created date the metrics will be the same like the ID and the distinct count and hit create so we have basically the same we did previously but now what we can do is go to Advanced analytics and add a rolling window so we want the cumulative sum we want it to be based on every day let's hit update chart but I have an error because I need to set a start and end date so here on my filters let's add a time range I have different options available let's select last and I can select last day last week last month so let's say a last month apply save and update the chart so now we have the cumulative number of users So currently I have a I have a total of five users and we see it growing over time even if it's very simple data we also have that second line that shows compared to the previous day how many we had okay let's hit save and create a last type of chart so this one is users progression over time save now let's create a new chart but to do it we will need to add the data set from the sales so connect data sets okay schema public and add the sales so it contains the user ID you just integer it's not a real linked table the amount of sales in the total and the number of products now we can say we want a bigger number from it and create a new chart this one is pretty simple so what kind of metric do we want to display well it's not the correct data sets it's using another chart Source public clean sales data it's not the correct one so let's create another one choose uh says okay this one big number create new chart metric simple the amount and we want the sum up all the C's create chart and we can see how much in total did we sell then we can customize the way it looks so tiny normal huge if you want to make it very big and it's here it's not that useful but when you will use it in your dashboard it will be quite useful so the sub header bit here we don't have one we can select the way that digits are displayed for this use case it's an amount so we can add the dollar sign hit update chart and save it total says and Save now unfortunately if we want to create a data based on two tables for example link the says with users compared to metabase where you could easily do it and say on what column the relation is based here you can't do it you used data sets so you can create yours but you have to build them using SQL lab what it is is an SQL editor where you will write your requests and being able to save it so let's select our database so we don't want the example we want our public that we connected we can select that schema to be able to to preview it and write the correct syntax but it's up to us to write the query but I know our table so select public dot says and we will take all column and we will also well here there's a mistake okay we will also take uh the username but we don't have it so we take this from the sales table and we join our users from it we will join users the link is made on users.id is equal to public dot says dot user ID and let's say we limit it to 100 okay so run and here we can see the results of what we did we have all the those columns are from the says so until number of products and the name is coming from our linked table we can try to save it we can save it into a data set let's say users sale with name save and explore now we have some data sets let's create our dashboard using it with our examples we will look at them later but go to create new dashboard and here it's a bit like metabase you have your data sets or some layout elements and you're able to create your dashboard from it so let's use the total number of sales users progressions over time the new users per day we can also add some layout elements like a title you can add some texts to explain what it is you can add header and layout the way you want it to be and have it available at any time let's hit save because we have fake data it's not that interesting so let's have a look at the examples we have slack dashboard it looks way better to the one I created so here we can see they added a logo some Trends the time zones for members messages per Channel so here I'd say the main difference with metabase is they are able to create a very Advanced kind of graphs using data so look at this one it's it's huge but it's not easy for everyone to create those data sets and to be used there is also that second example video game cell so here we have the text with the title subtitle original data set the global sales per console so what would be used a lot of metrics here what are the top 10 games you have pie charts a lot of different kind of charts and it looks good out of the box once you have your data set correctly something that you can do on metabase and that you can do here as well is to add filters so let's say you want only those sales of this here you will select a Time range name it correctly and add the settings of what time range you want and that way you will have the data updated to those features and it will be very dynamic last thing to have a look at are the settings so we already saw how to connect a database but you can also add some users to it so by default it created the admin but you can add other users with other sets of permission here is the form creation for a simple user but you have roles available and it's a very fine-grained one so let's have a look at the raw level security you can Define from here on what table what roles are available to do and see so it's quite powerful but yet it's still not a very easy to do you can also customize the interface so adding some CSS templates to your charts and interface you can add some alerts and a report based on your data and run Cron job wrapping up superset is a superb tool for SQL data visualization with really Advanced charge possibilities and fine grain control over users and roles but for most cases and kind of users we'd recommend the use of metabase for its better flexibility and ease of use if you haven't watched our video covering metabase I highly recommend you to do so to Choose Wisely which platform is more adapted to your needs by clicking here.

# Resumo

## 1. Introdução e Objetivo

- **Título:** Como construir dashboards de visualização de dados para o seu banco de dados
- **Ferramenta:** Apache Superset – uma ferramenta open source gratuita para transformar bancos de dados SQL em gráficos e dashboards interativos
- **Objetivo do Vídeo:**
    - Demonstrar como implantar uma instância do Superset
    - Conectar seu banco de dados
    - Criar conjuntos de dados, gráficos e dashboards
    - Destacar prós e contras da ferramenta em comparação com o Metabase

---

## 2. Implantação da Instância do Superset

- **Acesso e Criação:**
    - Acesse o site ls.io e clique em **Login**
    - Já existe uma instância de Postgres disponível para uso
    - Crie um novo serviço, pesquise por "superset" e selecione-o
    - Escolha seu provedor de cloud (ex.: Scaleway)
    - Defina o nível de suporte desejado e clique em **Create Service**
- **Notificação:**
    - Você receberá um e-mail assim que sua instância estiver implantada
    - O e-mail contém a senha para acessar o dashboard

---

## 3. Acesso ao Superset e Configuração Inicial

- **Primeiro Acesso:**
    - Copie a senha do e-mail e acesse a interface administrativa do Superset
    - O usuário é automaticamente criado (geralmente utilizando o e-mail de login)
- **Observação:**
    - Ao primeiro acesso, o dashboard estará vazio – ele é populado conforme você cria dashboards e gráficos

---

## 4. Conectando seu Banco de Dados

- **Procedimento:**
    - No menu **Data Sets**, clique em **Connect Database**
    - Escolha entre os bancos de dados relacionais (sempre baseados em SQL)
    - Exemplo utilizado: Postgres (as informações estão na instância do ls.io)
- **Demonstração:**
    - Visualize as informações administrativas do banco para copiar os dados de conexão
    - Teste a conexão; ao ser bem-sucedida, o Superset oferecerá opções para criar um conjunto de dados ou usar o SQL Lab

---

## 5. Criação de Conjuntos de Dados e Gráficos

### 5.1 Criação de Conjunto de Dados

- **Seleção de Tabelas:**
    - Selecione o banco de dados conectado (ex.: Postgres) e o schema (ex.: `public`)
    - Exemplo: Tabelas criadas para **sales** (vendas) e **users** (usuários)
- **Análise Inicial:**
    - Visualize as colunas e os tipos de dados para confirmar que estão corretos

### 5.2 Criação de Gráficos

- **Opções de Gráficos Disponíveis:**
    
    - Gráficos do tipo Big Number, Tabela, Linha, Barra, Área, entre outros
- **Exemplo Prático – Usuários:**
    
    - **Big Number com Linha de Tendência:**
        - Seleciona métrica: contagem distinta da coluna ID
        - Resultado: exibe “1” (último valor), porém, comparando datas (ex.: 21º e 22º dia), percebe-se a diferença; se necessário, mudar para gráfico de barras para visualizar a quantidade de novos usuários por dia
    - **Gráfico de Linha:**
        - No eixo X, utilizar a data de criação
        - Adicionar análise avançada (rolling window) para soma cumulativa
        - Ajustar filtros (definir intervalo de tempo – ex.: “último mês”) para que o gráfico apresente a progressão cumulativa dos usuários
- **Exemplo Prático – Vendas:**
    
    - Selecionar a tabela de **sales**
    - Criar um gráfico do tipo Big Number para exibir o total de vendas (soma dos valores)
    - Personalizar a visualização (tamanho, formatação, adição de símbolo de dólar)

---

## 6. Criação de Conjunto de Dados a Partir de Múltiplas Tabelas

- **Desafio:**
    - Combinar informações de duas tabelas (por exemplo, relacionar vendas com usuários)
- **Solução:**
    - Utilizar o **SQL Lab** para escrever uma query manual que faça o JOIN entre as tabelas
    - Exemplo:
        - Selecionar todas as colunas da tabela de vendas (ex.: `public.sales`)
        - Realizar JOIN com a tabela de usuários, onde `users.id` é igual a `sales.user_id`
        - Limitar o número de registros (ex.: LIMIT 100)
    - Salvar a query como um novo conjunto de dados, permitindo a criação de gráficos integrados

---

## 7. Montagem do Dashboard

- **Criação:**
    
    - Clique em **Create New Dashboard**
    - Adicione os gráficos e conjuntos de dados criados (ex.: total de vendas, progressão de usuários, novos usuários por dia)
- **Personalização do Layout:**
    
    - Adicione elementos de layout, como títulos, textos e blocos de markdown para explicar os dados
    - Organize os gráficos conforme o design desejado
- **Exemplos de Dashboards:**
    
    - Comparação com exemplos do Metabase (ex.: dashboards com logo, tendências, informações de membros, etc.)
    - Outros exemplos podem incluir dashboards de vendas globais ou de consoles de videogame, mostrando métricas detalhadas e gráficos variados

---

## 8. Filtros e Dinamismo

- **Adição de Filtros:**
    - Permite que os dashboards sejam dinâmicos, filtrando dados por intervalo de tempo, categoria ou outros parâmetros
    - Exemplo: definir um filtro para exibir apenas vendas em um determinado período
- **Interatividade:**
    - Os filtros podem ser aplicados de forma global no dashboard ou configurados para afetar somente alguns gráficos
    - Isso torna a visualização dos dados mais interativa e adaptada às necessidades do usuário

---

## 9. Configurações, Segurança e Customização

- **Gerenciamento de Usuários:**
    - Criação de usuários adicionais com diferentes permissões
    - Sistema de roles para controle de acesso granular aos dados e dashboards
- **Customização da Interface:**
    - Adição de templates CSS para personalizar gráficos e a interface
    - Configuração de alertas e relatórios (por exemplo, envio automático via e-mail ou Slack)
- **Outras Configurações:**
    - Agendamento de atualizações, exportação de dados, uso de feature flags para habilitar funcionalidades avançadas

---

## 10. Considerações Finais

- **Resumo:**
    - O Apache Superset é uma ferramenta poderosa para visualização de dados SQL, com muitas opções avançadas e controle fino sobre usuários e dashboards
    - Apesar de sua flexibilidade e robustez, pode ser menos intuitivo para iniciantes em comparação com ferramentas como o Metabase
- **Recomendação:**
    - Escolha a plataforma que melhor se adapta às suas necessidades:
        - Superset para personalizações avançadas e controle detalhado
        - Metabase para facilidade de uso e interface mais amigável
- **Encerramento:**
    - Convidar o espectador a explorar a documentação oficial e a comunidade do Superset para mais informações e suporte