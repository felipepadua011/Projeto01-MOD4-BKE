# Projeto01-MOD4-BKE

**Olá, este projeto consiste em desenvolver uma API com armazenamento em banco de dados. Utilizando a Integração Backend + Postgreesql.** 

**Onde existirão 3 rotas principais:** 

 **Rota Filmes.** 

 **Rota Genero.** 

 **Rota Participantes.**



 **Dentro de cada rota temos possuimos 4 funções:**

 `CREATE` 	**Utilizano o método POST.**

 `UPDATE ` 	**Utilizano o método PATCH.**

`GET ALL`  	**Utilizano o método GET.**

`GET`  	    **Utilizano o método GET.**

`DELETE` 	  **Utilizano o método DELETE.**



**A rota filmes  `/filmes`**  **, necessita de:**

​				**`/filmes`**   **Utilizano o método POST.**

- ​	**Usado para adicionar um novo filmes ao banco de dados.**

- ​    **Exemplo:**    `/filmes`

- ​    **Para adicionar um filme dentro do banco, necessita passar todos os dados com suas devidas informações a seguir:**

  ```javascript
  {
      "nome": "Teste2",
      "imagem": "Teste1.jpg",
      "datlanca": "09/12/2021",
      "tempdura": "1h56min",
      "generoid": 1,
      "participanteid": 1
  }
  ```

  

- ​    **Se for adicionado retornará um .json com as informações e um status 201.**

  ```javascript
  {
      "nome": "Teste2",
      "imagem": "Teste1.jpg",
      "datlanca": "09/12/2021",
      "tempdura": "1h56min",
      "generoid": 1,
      "participanteid": 1
  }
  ```

​				**`/filmes`** 

- ​	**Usado para visualizar todos os filmes cadastrados no banco.**

- ​    **Exemplo:**    `/filmes`   **Utilizano o método GET.**

- ​	**Após ser executado, retornará um .json com todos os filmes INCLUINDO UM ID, cada filmes possui seu ID criado automaticamente pelo banco.**

  ```javascript
  {
    "id": 3,
    "nome": "Homem Aranha 2",
    "imagem": "aranha2.jpg",
    "datlanca": "18/12/2021",
    "tempdura": "2h56min",
    "generoid": 4,
    "participanteid": 3
  }
  ```

- **Caso não tenha nada cadastrado no banco, irá retornar um .json vazio.**

  ```javascript
  [];
  ```

  

​				**`/filmes/:id`** 

- ​	**/:id  , Na url precisamos passar o id do item que deseja visualizar.**  

  **Exemplo:**      `/filmes/3`   **Utilizano o método GET.**

  - ​**Usado quando o usuário deseja achar um filme específico usando apenas seu id, sem necessitar de outras informações.**

  - **Caso não exista nenhum filme cadastrado no banco com o nome id, irá retornar um .json vazio.**


  ```javascript
  {
  "id": 3,
  "nome": "Homem Aranha 2",
  "imagem": "aranha2.jpg",
  "datlanca": "18/12/2021",
  "tempdura": "2h56min",
  "generoid": 4,
  "participanteid": 3
}
  ```


​			**`/filmes/:id`** 

- ​	**/:id  , Na url precisamos passar o id do item em que deseja atualizar, sendo esse FIXO, INALTERÁVEL**

  **Exemplo:**      `/filmes/3`   **Utilizano o método PATCH.**

-    **Usado para atualizar informações já existentes no banco de dados.**

- **Para atualizar esses dados NÃO é necessário passar todos os dados, o método PATCH permite que você altere apenas um campo por vez se desejar:**

  ```javascript
    {
      "nome": "",  //(Type: String)
      "imagem": "",  //(Type: String)
      "datlanca": "",  //(Type: String)
      "tempdura": "",  //(Type: String)
      "generoid": ,  //(Type: Number)
      "participanteid":   //(Type: Number)
    }
  ```

- ​ **Se for atualizado retornará um .json mostrando todas as novas informações e um status 200.**

  ```javascript
  {
      "nome": "",  //(Type: String)
      "imagem": "",  //(Type: String)
      "datlanca": "",  //(Type: String)
      "tempdura": "",  //(Type: String)
      "generoid": ,  //(Type: Number)
      "participanteid":   //(Type: Number)
    }
  ```

- **Caso contrário não for atualizado no banco, retornará um status de erro 400.**


​		**`/filmes/:id`** 

- ​	**/:id  , Na url precisamos passar o id do item em que deseja atualizar, sendo esse FIXO, INALTERÁVEL**

  **Exemplo:**      `/filmes/3`   **Utilizando o método DELETE.**

-    **Utilizamos o delete quando queremos remover algum filme já cadastrado no banco.**

- **Caso o ID passado exista no banco, ele irá remove-lô do banco, ação irreversível e retornará um status 200 de confirmação.**


- ​     **Porém se o ID passado na url não existir no banco, ele não irá achar nada para deletar assim retornando um status 400 de erro.**



**A rota genero  `/genero`**  **, necessita de:**

​				**`/genero`**   **Utilizano o método POST.**

- **Exemplo:**    `/genero`

- ​	**Usado para adicionar um novo genero ao banco de dados.**

- ​    **Para adicionar um genero dentro do banco, necessita passar todos os dados com suas devidas informações a seguir:**

  ```javascript
  {
  "nome": "Comédia"
  }
  ```


- ​    **Se for adicionado retornará um .json com as informações e um status 201.**

  ```javascript
  {
    "nome": "Comédia"
  },
  ```

  
​				**`/genero`** 

- ​	**Usado para visualizar todos os generos cadastrados no banco.**

- ​    **Exemplo:**    `/genero`   **Utilizano o método GET.**

- ​	**Após ser executado, retornará um .json com todos os generos INCLUINDO UM ID, cada genero possui seu ID criado automaticamente pelo banco.**

  ```javascript
  {
    "id": 4,
    "nome": "comédia"
  },
  ```

- **Caso não tenha nada cadastrado no banco, irá retornar um .json vazio.**

  ```javascript
  [];
  ```

  

​				**`/genero/:id`** 

- ​	**/:id  , Na url precisamos passar o id do item que deseja visualizar.**  

  **Exemplo:**      `/genero/4`   **Utilizano o método GET.**

  ```javascript
  {
    "id": 4,
    "nome": "comédia"
  },
  ```


- ​	**Usado quando o usuário deseja achar um genero específico usando apenas seu id, sem necessitar de outras informações.**



​			**`/genero/:id`** 

- ​	**/:id  , Na url precisamos passar o id do item em que deseja atualizar, sendo esse FIXO, INALTERÁVEL**

  **Exemplo:**      `/genero/4`   **Utilizando o método PATCH.**

- **Usado para atualizar informações já existentes no banco de dados.**

- **Para atualizar esses dados NÃO é necessário passar todos os dados, o método PATCH permite que você altere apenas um campo por vez se desejar:**


  ```javascript
  {
    "nome": "",  //(Type: String)
  }
  ```

  
- ​ **Se for atualizado retornará um .json mostrando todas as novas informações e um status 200.**

  ```javascript
   {
    "nome": "",  //(Type: String)
  }
  ```

  

​		**`/genero/:id`** 

- ​	**/:id  , Na url precisamos passar o id do item em que deseja atualizar, sendo esse FIXO, INALTERÁVEL**

  **Exemplo:**      `/genero/4`   **Utilizando o método DELETE.**

-  **Utilizamos o delete quando queremos remover algum genero já cadastrado no banco.**

- **Caso o ID passado exista no banco, ele irá remove-lô do banco, ação irreversível e retornará um status 200.**

- ​**Porém se o ID passado na url não existir no banco, ele não irá achar nada para deletar assim retornando um status 400 de erro.**






**A rota participantes  `/participantes`**  **, necessita de:**

​				**`/participantes`**   **Utilizano o método POST.**

- ​	**Usado para adicionar um novo participante ao banco de dados.**

- ​    **Exemplo:**    `/participante`

- ​    **Para adicionar um participante dentro do banco, necessita passar todos os dados com suas devidas informações a seguir:**

  ```javascript
  {
  "nome": "Homem Aranha",           
  "imagem": "aranha.jpg",           
  "datanasc": "12/12/2000",        
  "ator": "Peter Park"          
}
  ```

  

- ​    **Se for adicionado retornará um .json com as informações e um status 201.**

  ```javascript
  {
  "id": 4,
  "nome": "Homem Aranha",
  "imagem": "aranha.jpg",
  "datanasc": "12/12/2000",
  "ator": "Peter Park"
}
  ```

​				**`/participantes`** 

- ​	**Usado para visualizar todos os participante cadastrados no banco.**

- ​    **Exemplo:**    `/participantes`   **Utilizano o método GET.**

- ​	**Após ser executado, retornará um .json com todos os participante INCLUINDO UM ID, cada participante possui seu ID criado automaticamente pelo banco.**

  ```javascript
  {
  "id": 4,
  "nome": "Homem Aranha",
  "imagem": "aranha.jpg",
  "datanasc": "12/12/2000",
  "ator": "Peter Park"
}
  ```

- **Caso não tenha nada cadastrado no banco, irá retornar um .json vazio.**

  ```javascript
  [];
  ```

  

​				**`/participantes/:id`** 

- ​	**/:id  , Na url precisamos passar o id do item que deseja visualizar.**  

  **Exemplo:**      `/participantes/4`   **Utilizano o método GET.**

  - ​**Usado quando o usuário deseja achar um participante específico usando apenas seu id, sem necessitar de outras informações.**

  - **Caso não exista nenhum participante cadastrado no banco com o nome id, irá retornar um .json vazio.**


  ```javascript
{
  "id": 4,
  "nome": "Homem Aranha",
  "imagem": "aranha.jpg",
  "datanasc": "12/12/2000",
  "ator": "Peter Park"
}
  ```


​			**`/participantes/:id`** 

- ​	**/:id  , Na url precisamos passar o id do item em que deseja atualizar, sendo esse FIXO, INALTERÁVEL**

  **Exemplo:**      `/participantes/4`   **Utilizano o método PATCH.**

-    **Usado para atualizar informações já existentes no banco de dados.**

- **Para atualizar esses dados NÃO é necessário passar todos os dados, o método PATCH permite que você altere apenas um campo por vez se desejar:**

  ```javascript
    {
      "nome": "Homem Aranha",   //(Type: String)
      "imagem": "aranha.jpg",   //(Type: String)
      "datanasc": "12/12/2000",   //(Type: String)
      "ator": "Peter Park"   //(Type: String)
    }
  ```

- ​ **Se for atualizado retornará um .json mostrando todas as novas informações e um status 200.**

  ```javascript
  {
      "nome": "",  //(Type: String)
      "imagem": "",  //(Type: String)
      "datnasc": "",  //(Type: String)
      "ator": ""  //(Type: String)
    }
  ```

- **Caso contrário não for atualizado no banco, retornará um status de erro 400.**


​		**`/participantes/:id`** 

- ​	**/:id  , Na url precisamos passar o id do item em que deseja atualizar, sendo esse FIXO, INALTERÁVEL**

  **Exemplo:**      `/participantes/4`   **Utilizando o método DELETE.**

-    **Utilizamos o delete quando queremos remover algum participante já cadastrado no banco.**

- **Caso o ID passado exista no banco, ele irá remove-lô do banco, ação irreversível e retornará um status 200 de confirmação.**


- ​     **Porém se o ID passado na url não existir no banco, ele não irá achar nada para deletar assim retornando um status 400 de erro.**



  

## **Para Iniciar o Projeto Local Foi Necessário Instalar Os Seguintes Comandos**

**`npm i -g @nestjs/cli`**      (Instalando as depedencias do NestJs).

**`nest g resource <nome da pasta>`**    (Criará os arquivos utilizados na sua API).

**`npm install prisma --save-dev`**     (Instalando as depedencias do Prisma).

**`npx prisma init`**  (Criará os arquivos utilizados pelo Prisma).

**`npm i dotenv`**     (Instala a lib para tratativa de var de ambiente).



#####                                                                                                    Trabalho Realizado Solo:

​                                                               Felipe Pereira de Pádua

######                      Esperamo ter ajudado na compreensão básica de como funciona este projeto e o que consta em suas dependencias internas.