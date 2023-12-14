# All For One

Temos, nesse projeto, uma série de desafios com diferentes níveis de complexidade que foram resolvidos cada um em seu arquivo próprio.
Na raiz do projeto existe vários arquivos chamados desafioN.sql, em que N é o número do desafio;

## 🚀 Começando

> - ⚠️ É necessário ter a versão Node 16.14 ou superior instalada localmente.

<br />

<details>
  <summary><strong>🔧 Instalação</strong></summary>
<br />
  
1. Clone o repositório
  * `git clone git@github.com:Wesleyhmendes/all-for-one-back-end.git`.
  * Entre na pasta do repositório que você acabou de clonar:
    * `cd all-for-one-back-end`

2. Instale as dependências [**Caso existam**]
  * `npm install`

3. Crie uma branch a partir da branch `master`
  * Verifique que você está na branch `master`
    * Exemplo: `git branch`
  * Se não estiver, mude para a branch `master`
    * Exemplo: `git checkout master`
  * Agora crie uma branch com o nome desejado

<br />
</details>

<br />

<details>
  <summary><strong>:whale: Rodando no Docker vs Localmente</strong></summary><br />

## Com Docker

  **:warning: Antes de começar, seu docker-compose precisa estar na versão 1.29 ou superior. [Veja aqui](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-compose-on-ubuntu-20-04-pt) ou [na documentação](https://docs.docker.com/compose/install/) como instalá-lo. No primeiro artigo, você pode substituir onde está com `1.26.0` por `1.29.2`.**

  > :information_source: Rode os serviços `node` e `db` com o comando `docker-compose up -d`.

- Lembre-se de parar o `mysql` se estiver usando localmente na porta padrão (`3306`), ou adapte, caso queria fazer uso da aplicação em containers
- Esses serviços irão inicializar um container chamado `all_for_one` e outro chamado `all_for_one_db`.
- A partir daqui você pode rodar o container `all_for_one` via CLI ou abri-lo no VS Code.

  > :information_source: Use o comando `docker exec -it all_for_one bash`.

- Ele te dará acesso ao terminal interativo do container criado pelo compose, que está rodando em segundo plano.
- As credencias de acesso ao banco de dados estão definidas no arquivo `docker-compose.yml`, e são acessíveis no container através das variáveis de ambiente `MYSQL_USER` e `MYSQL_PASSWORD`. 💡

  > :information_source: Instale as dependências [**Caso existam**] com `npm install`. (Instale dentro do container)

- **:warning: Atenção:** Caso opte por utilizar o Docker, **TODOS** os comandos disponíveis no `package.json` (npm start, npm test, npm run dev, ...) devem ser executados **DENTRO** do container, ou seja, no terminal que aparece após a execução do comando `docker exec` citado acima.

- **:warning: Atenção:** O **git** dentro do container não vem configurado com suas credenciais. Ou faça os commits fora do container, ou configure as suas credenciais do git dentro do container.

- **:warning: Atenção:** Não rode o comando npm audit fix! Ele atualiza várias dependências do projeto, e essa atualização gera conflitos com o avaliador.

  <br />

## Sem Docker

  > :information_source: Instale as dependências [**Caso existam**] com `npm install`

- **:warning: Atenção:** Não rode o comando npm audit fix! Ele atualiza várias dependências do projeto, e essa atualização gera conflitos com o avaliador.

- **✨ Dica:** Para rodar o projeto desta forma, obrigatoriamente você deve ter o `node` instalado em seu computador.
- **✨ Dica:** O avaliador espera que a versão do `node` utilizada seja a 16.

<br/>

</details> 

<details>
  <summary><strong>📋 Requisitos</strong></summary>
<br />

**1 - Exiba apenas os nomes dos produtos na tabela `products`.**

  ---

**2 - Exiba os dados de todas as colunas da tabela `products`.**

  ---

**3 - Escreva uma query que exiba os valores da coluna que representa a _primary key_ da tabela `products`.**

  ---

**4 - Conte quantos registros existem na coluna `product_name` da tabela `products`.**

  ---

**5 - Monte uma query que exiba os dados da tabela `products` a partir do quarto registro até o décimo terceiro.**

  ---

**6 - Exiba os dados das colunas `product_name` e `id` da tabela `products` de maneira que os resultados estejam em ordem alfabética dos nomes.**

  ---

**7 - Mostre apenas os ids dos 5 últimos registros da tabela `products` (a ordenação deve ser baseada na coluna `id`).**

  ---

**8 - Faça uma consulta na tabela `employees` que retorne o nome completo da pessoa colaboradora (colunas `first_name` e `last_name`) com o nome `full_name` e também a localização completa (colunas `city`, `state_province` e `address`) com o nome `location`.**

## Desafios sobre filtragem de dados

**9 - Mostre todos os valores de `notes` da tabela `purchase_orders` que não são nulos.**

  ---

**10 - Mostre todos os dados da tabela `purchase_orders` em ordem decrescente, ordenados por `created_by` em que o `created_by` é maior ou igual a 3.**

- Ordene também os resultados pelo `id` de forma crescente, como critério de desempate para a ordenação.

  ---

**11 - Exiba os dados da coluna `notes` da tabela `purchase_orders` em que seu valor de `Purchase generated based on Order` é maior ou igual a 30 e menor ou igual a 39.**

- ✨ Dica: `Purchase generated based on Order` é um valor atribuído à coluna `notes` e não uma coluna.

  ---

**12 - Mostre as `submitted_date` de `purchase_orders` em que a `submitted_date` é do dia 26 de abril de 2006.**

  ---

**13 - Mostre o `supplier_id` das `purchase_orders` em que o `supplier_id` seja 1 ou 3.**

  ---

**14 - Mostre os resultados da coluna `supplier_id` da tabela `purchase_orders` em que o `supplier_id` seja maior ou igual a 1 e menor ou igual 3.**

  ---

**15 - Mostre somente as horas (sem os minutos e os segundos) da coluna `submitted_date` de todos registros da tabela `purchase_orders`.**

- No resultado, a hora extraída da coluna `submitted_date` deve ser chamada de `submitted_hour`.

  ---

**16 - Exiba a `submitted_date` das `purchase_orders` que estão entre `2006-01-26 00:00:00` e `2006-03-31 23:59:59`.**

  ---

**17 - Mostre os registros das colunas `id` e `supplier_id` das `purchase_orders` em que os `supplier_id` sejam tanto 1, ou 3, ou 5, ou 7.**

  ---

**18 - Mostre todos os registros de `purchase_orders` que tem o `supplier_id` igual a 3 e `status_id` igual a 2.**

  ---

**19 - Mostre a quantidade de pedidos que foram feitos na tabela `orders` pelo `employee_id` igual a 5 ou 6, e que foram enviados através do método(coluna) `shipper_id` igual a 2.**

- No resultado, a coluna que contém a contagem de pedidos deve ser chamada de `orders_count`.

  ---

## Desafios de manipulação de tabelas

**20 - Adicione à tabela `order_details` um registro com `order_id`: 69, `product_id`: 80, `quantity`: 15.0000, `unit_price`: 15.0000, `discount`: 0, `status_id`: 2, `date_allocated`: NULL, `purchase_order_id`: NULL e `inventory_id`: 129.**

- ✨ Dica: O `id` deve ser incrementado automaticamente. Para entender melhor isso, você pode consultar o arquivo de criação da tabela (./northwind.sql, na linha 439) [aqui](northwind.sql).

  ---

**21 - Adicione com um único `INSERT`, duas linhas à tabela `order_details` com os mesmos dados do requisito 20.**

  ---

**22 - Atualize todos os dados da coluna `discount`, na tabela `order_details`, para 15.**

  ---

**23 - Atualize os dados da coluna `discount` da tabela `order_details` para 30, onde o valor na coluna `unit_price` seja menor que 10.0000.**

- ✨ Dica: Não é necessário utilizar o SAFE UPDATE em sua query.

  ---

**24 - Atualize os dados da coluna `discount` da tabela `order_details` para 45, onde o valor na coluna `unit_price` seja maior que 10.0000 e o id seja um número entre 30 e 40.**

- ✨ Dica: Não é necessário utilizar o SAFE UPDATE em sua query.

  ---

**25 - Delete todos os dados em que a `unit_price` da tabela `order_details` seja menor que 10.0000.**

  ---

**26 - Delete todos os dados em que a `unit_price` da tabela `order_details` seja maior que 10.0000.**

  ---

**27 - Delete todos os dados da tabela `order_details`.**

  ---

</details>

## 🛠️ Construído com

Mencione as ferramentas que você usou para criar seu projeto

* [npm](https://www.npmjs.com/) - Gerente de Dependência

## 📌 Versão

Nós usamos [Docker](https://www.docker.com/) para controle de versão.

## ✒️ Autores

* **Wesley Mendes** - *Trabalho Inicial* - [Wesley Mendes](https://github.com/Wesleyhmendes)
