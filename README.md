# Boas-vindas ao repositório do projeto Docker Todo List!

# Entregáveis

<details>
  <summary><strong>👨‍💻 O que deverá ser desenvolvido</strong></summary><br />

Neste projeto você irá:

1. **_Conteinerizar_** aplicações;
2. Criar uma conexão entre elas;
3. Orquestrar seu funcionamento.

Temos [uma aplicação full-stack](docker/todo-app) neste repositório: um **aplicativo de tarefas**! Esta aplicação precisa ser conteinerizada para funcionar. Você deverá desenvolver os arquivos de configuração para cada frente específica: `Front-end`, `Back-end` e, no nosso caso, para um aplicativo de `teste` que valida se as aplicações estão se comunicando.

---

Você deverá criar as imagens para as aplicações e configurar essas imagens com o `docker-compose`.

Para isto, você irá utilizar uma série de comandos do `docker` com diferentes níveis de complexidade.

Cada comando deverá ser escrito em seu próprio arquivo.

Para isto, siga os seguintes passos:

1. Leia o requisito e crie um arquivo chamado `commandN.dc` no diretório `docker-commands`, onde `N` é o número do requisito. Por exemplo:

    ```text
    Requisito 1: ./docker/docker-commands/command01.dc
    Requisito 2: ./docker/docker-commands/command02.dc
    Requisito 3: ./docker/docker-commands/command03.dc
    ```
    **⚠️ É muito importante que os seus arquivos tenham exatamente estes nomes! ⚠️**


2. Escreva neste arquivo o comando do CLI *(Interface de Linha de Comando)* do Docker que resolve o requisito. Um exemplo de como vai ficar seu arquivo:

    ```dc
    docker network inspect bridge
    ```

---

Os arquivos principais do projeto estão na pasta `docker`, na raiz do projeto. Nela estão contidos:

1. Pasta `docker-commands`: onde ficarão os comandos exigidos pelos requisitos;
   - **⚠️ Importante: você deve assumir que essa é a pasta raiz para os comandos.**
   - Por exemplo, se você precisa referenciar um caminho em um comando, você deve assumir que sua pasta raiz esta partindo de `./docker`.
2. Pasta `todo-app`: onde fica a nossa **pseudo-aplicação**, que servirá como base para nossos `Dockerfile`s e `Compose`;
   - **⚠️ Essa aplicação conta com um [**README.md**](./docker/todo-app/README.md) próprio, que pode ser usado como referência na criação dos `dockerfiles` e do `docker-compose.yml`!**

Quando for necessário fazer a orquestração das aplicações, o arquivo `docker-compose.yml` deverá ser criado na pasta `./docker`. conforme o arquivo de exemplo [`docker/docker-compose.yml.example`](docker/docker-compose.yml.example).

</details>

# Orientações

<details>
  <summary><strong>‼️ Antes de começar a desenvolver</strong></summary><br />

1. Clone o repositório
* `git clone git@github.com:tryber/sd-025-b-project-docker-todo-list.git`
* Entre na pasta do repositório que você acabou de clonar:
  * `cd sd-025-b-project-docker-todo-list`

2. Instale as dependências:
  * `npm install`

* Verifique se os testes estão executando:
  * `npm test` (os testes devem rodar e falhar)

3. Crie uma branch a partir da branch `master`

* Verifique que você está na branch `master`
  * Exemplo: `git branch`
* Se não estiver, mude para a branch `master`
  * Exemplo: `git checkout master`
* Agora, crie uma branch onde você vai guardar os commits do seu projeto
  * Você deve criar uma branch no seguinte formato: `nome-de-usuario-nome-do-projeto`
  * Exemplo:
    * `git checkout -b joaozinho-sd-025-b-project-docker-todo-list`

4. Adicione a sua branch com o novo `commit` ao repositório remoto

- Usando o exemplo anterior:
  - `git push -u origin joaozinho-sd-025-b-project-docker-todo-list`

5. Crie um novo `Pull Request` _(PR)_
* Vá até a página de _Pull Requests_ do repositório no GitHub: [docker-todo-list](https://github.com/tryber/sd-025-b-project-docker-todo-list/pulls)
* Clique no botão verde _"New pull request"_
* Clique na caixa de seleção _"Compare"_ e escolha a sua branch **com atenção**
* Clique no botão verde _"Create pull request"_
* Adicione uma descrição para o _Pull Request_ e clique no botão verde _"Create pull request"_
* **Não se preocupe em preencher mais nada por enquanto!**
* Volte até a [página de _Pull Requests_ do repositório](https://github.com/tryber/sd-025-b-project-docker-todo-list/pulls) e confira que o seu _Pull Request_ está criado

</details>

<details>
  <summary><strong>🛠 Testes</strong></summary><br />

⚠ **É necessário ter o Docker instalado corretamente na sua máquina para rodar os testes locais**.

Todos os requisitos do projeto serão testados automaticamente por meio do Jest. Basta executar o comando abaixo:

```bash
npm test
```

Você pode rodar um arquivo de `test` por vez, exemplo:

```bash
npm test 01container
```
⚠ **Atenção:** ⚠
Não utilize a função `.only` ou `.skip` após o describe. Os testes precisam rodar por completo para que o projeto seja avaliado localmente.

</details>

# Requisitos obrigatórios do projeto

## Comandos docker

⚠ Lembre-se das instruções da seção [Entregáveis](#Entregáveis), especialmente no tópico `O que deverá ser desenvolvido`!

### 1. Crie um container em modo interativo, sem rodá-lo, nomeando-o como `01container` e utilizando a imagem `alpine` na versão `3.12`

<details>
  <summary>➕ Informações adicionais</summary><br />

O avaliador executará o comando no arquivo `command01.dc`.

#### Observações técnicas

- O container **não deve ser inicializado**, somente criado;
- O container deve estar preparado para acesso interativo.

#### Dicas
- Dê uma olhada no comando [`create`](https://docs.docker.com/engine/reference/commandline/create/). 😉
- Lembre-se que um parâmetro não é necessariamente aplicável a apenas um comando;
- Consulte sempre que possível a [Documentação Oficial](https://docs.docker.com/engine/reference/commandline/docker/) sobre comandos básicos;
- Lembre-se que a esmagadora parte dos comandos docker recebe parâmetros (opções), como [nesse exemplo](https://docs.docker.com/engine/reference/commandline/logs/#options).

#### O que será testado

- O `nome` do container deve ser `01container`;
- O container deve usar a imagem `alpine` na versão `3.12`;
- O `status` do container deve ser `created`;
- O container **não deve** estar em execução após ter sido criado.

</details>

### 2. Inicie o container `01container`

<details>
  <summary>➕ Informações adicionais</summary><br />

O avaliador executará o comando no arquivo `command02.dc`.

#### Observações técnicas

- O container `01container`, que acabou de ser criado e está parado, deve ser iniciado;
- Se o container tiver sido iniciado de modo interativo, ele deve se manter ativo ao iniciá-lo.
  
#### O que será testado

- O avaliador verificará se o container está parado;
- O avaliador executará o comando criado neste requisito;
- O container **deve** estar em execução.

</details>

### 3. Liste os containers filtrando pelo nome `01container`

<details>
  <summary>➕ Informações adicionais</summary><br />

O avaliador executará o comando no arquivo `command03.dc`.

#### Dicas

- Praticamente todo comando de listagem no Docker possui uma forma de filtragem.

#### O que será testado

- O comando deve retornar uma lista contendo informações **apenas** do `01container`.

</details>

### 4. Execute o comando `cat /etc/os-release` no container `01container` sem se acoplar a ele

<details>
  <summary>➕ Informações adicionais</summary><br />

O avaliador executará o comando no arquivo `command04.dc`.

#### Observações técnicas

- O container deve estar rodando e você deve ser capaz de **executar um comando** nesse container.

#### Dicas

- É possível fazer isso sem usar o comando `attach`.

#### O que será testado

- Que o comando retornará os dados corretos da `distro` no container:
  - `NAME="Alpine Linux"`
  - `ID=alpine`
  - `VERSION_ID=3.12`

</details>

### 5. Remova o container `01container`

<details>
  <summary>➕ Informações adicionais</summary><br />

O avaliador executará os comandos nos arquivos `command05.dc` e `command03.dc`.

#### O que será testado

- O avaliador rodará o comando 5;
- O avaliador validará o processo com o comando 3.

</details>

### 6. Faça o download da imagem `nginx` com a versão `1.21.3-alpine` sem criar ou rodar um container

<details>
  <summary>➕ Informações adicionais</summary><br />

O avaliador executará o comando no arquivo `command06.dc`.

#### O que será testado

  - Que a imagem correta foi baixada;
  - Que nenhum container foi iniciado para isso.

</details>

### 7. Rode um novo container com a imagem  `nginx` com a versão `1.21.3-alpine` em segundo plano nomeando-o como `02images` e mapeando sua porta padrão de acesso para porta `3000` do sistema hospedeiro

<details>
  <summary>➕ Informações adicionais</summary><br />

O avaliador executará o comando no arquivo `command07.dc`.

#### O que será testado

  - Que o container foi iniciado corretamente;
  - Que é possível ter acesso ao container pelo endereço `localhost:3000`;
  - Que a página retorna o valor esperado.

</details>

### 8. Pare o container `02images` que está em andamento

<details>
  <summary>➕ Informações adicionais</summary><br />

O avaliador executará o comando no arquivo `command08.dc`.

#### O que será testado

  - Que não há nenhum container ativo após seu comando.

</details>

## Dockerfile

**⚠️ As aplicações a seguir contam com um [**README.md**](./docker/todo-app/README.md) próprio, que deve ser usado como referência na criação dos scripts!**

### 9. Gere uma build a partir do Dockerfile do `back-end` do `todo-app` nomeando a imagem para `todobackend`

Escreva no arquivo `command09.dc` um comando que fará o `build`([documentação do comando](https://docs.docker.com/engine/reference/commandline/build/)) de uma imagem a partir do arquivo `./docker/todo-app/back-end/Dockerfile`, esta imagem deve ter o nome `todobackend`.

No arquivo `./docker/todo-app/back-end/Dockerfile` escreva os comandos que farão com que a imagem:
- rode a partir da imagem do `node` na versão 14;
- exponha a porta 3001;
- adicione o arquivo `node_modules.tar.gz` à imagem;
- copie todos os arquivos da pasta `back-end` para a imagem. (você pode usar o caminho relativo, lembrando que a `Dockerfile` está em `./docker/todo-app/back-end/Dockerfile`);
- inicie a aplicação com o comando `npm start`.

<details>
  <summary>➕ Informações adicionais</summary><br />

- Nesse contexto, deve-se criar um arquivo [`Dockerfile`](https://docs.docker.com/engine/reference/builder/#format) na pasta `./docker/todo-app/back-end/`, que será utilizado com comando exigido no requisito;
- Esse arquivo deve buscar reproduzir as etapas de `back-end` contidas no [`README.md`](docker/todo-app/README.md) da *pseudo-aplicação* (também estão descritas na seção `O que será testado`, do requisito) para que ele rode corretamente;
- O avaliador executará o comando no arquivo `command09.dc`.

#### Dicas 

- O [comando `ADD`](https://docs.docker.com/engine/reference/builder/#add) do Dockerfile, também pode ser utilizado para descompactar arquivos dentro do container.
  - Entenda a diferença entre o comando `ADD` e `COPY` [neste artigo](https://coderarena.com.br/posts/docker-tips-01-qual-e-a-diferenca-entre-add-e-copy/).

#### O que será testado

- Se existe um arquivo `Dockerfile` em `./docker/todo-app/back-end/`:
  - O Dockerfile deve rodar uma imagem `node` utilizando a versão `14`;
    - Recomenda-se o uso da variante `-alpine`, pois ela é otimizada para desempenho;
    - Lembre-se de consultar o README do `todo-app` para validar os requisitos da aplicação.
  - Deve estar com a porta `3001` exposta;
  - Deve adicionar o arquivo `node_modules.tar.gz` a imagem;
  - Deve copiar todos os arquivos da pasta `back-end` para a imagem;
  - Ao iniciar a imagem deve rodar o comando `npm start`.
- Se ao *buildar* o Dockerfile o nome da imagem gerada é igual a `todobackend`.

</details>

### 10. Gere uma build a partir do Dockerfile do `front-end` do `todo-app` nomeando a imagem para `todofrontend`

Escreva no arquivo `command10.dc` um comando que fará o `build`([documentação do comando](https://docs.docker.com/engine/reference/commandline/build/)) de uma imagem a partir do arquivo `./docker/todo-app/front-end/Dockerfile`, esta imagem deve ter o nome `todofrontend`.

No arquivo `./docker/todo-app/front-end/Dockerfile` escreva os comandos que farão com que a imagem:
- rode a partir da imagem do `node` na versão 14;
- exponha a porta 3000;
- adicione o arquivo `node_modules.tar.gz` à imagem;
- copie todos os arquivos da pasta `front-end` para a imagem. (você pode usar o caminho relativo, lembrando que a `Dockerfile` está em `./docker/todo-app/front-end/Dockerfile`);
- inicie a aplicação com o comando `npm start`.


<details>
  <summary>➕ Informações adicionais</summary><br />

- Nesse contexto, deve-se criar um arquivo [`Dockerfile`](https://docs.docker.com/engine/reference/builder/#format) na pasta `./docker/todo-app/back-end/`, que será utilizado com comando exigido no requisito;
- Esse arquivo deve buscar reproduzir as etapas de `front-end` contidas no [`README.md`](docker/todo-app/README.md) da *pseudo-aplicação* (também estão descritas na seção `O que será testado`, do requisito) para que ele rode corretamente;
- O avaliador executará o comando no arquivo `command10.dc`.

#### Dicas

- O [comando `ADD`](https://docs.docker.com/engine/reference/builder/#add) do Dockerfile, também pode ser utilizado para descompactar arquivos dentro do container.
  - Entenda a diferença entre o comando `ADD` e `COPY` [neste artigo](https://coderarena.com.br/posts/docker-tips-01-qual-e-a-diferenca-entre-add-e-copy/).
#### O que será testado

  - Se existe um arquivo `Dockerfile` em `./docker/todo-app/front-end/`:
    - O `Dockerfile` pode rodar uma imagem `node` utilizando a versão `14`;
      - Recomenda-se o uso da variante `-alpine`, pois ela é otimizada para desempenho;
      - Lembre-se de consultar o README do `todo-app` para validar os requisitos da aplicação.
    - Deve estar com a porta `3000` exposta;
    - Deve adicionar o arquivo `node_modules.tar.gz` a imagem, de maneira que ele seja extraído dentro do `container`;
    - Deve copiar todos os arquivos da pasta `front-end` para a imagem;
    - Ao iniciar a imagem deve rodar o comando `npm start`;
  - Se ao *buildar* o `Dockerfile` o nome da imagem gerada é igual a `todofrontend`.

</details>

### 11. Gere uma build a partir do Dockerfile dos `testes` do `todo-app` nomeando a imagem para `todotests`

Escreva no arquivo `command11.dc` um comando que fará o `build`([documentação do comando](https://docs.docker.com/engine/reference/commandline/build/)) de uma imagem a partir do arquivo `./docker/todo-app/tests/Dockerfile`, esta imagem deve ter o nome `todotests`.

No arquivo `./docker/todo-app/tests/Dockerfile` escreva os comandos que farão com que a imagem:
- rode a partir da imagem do `mjgargani/puppeteer:trybe1.0`;
- adicione o arquivo `node_modules.tar.gz` à imagem;
- copie todos os arquivos da pasta `tests` para a imagem. (você pode usar o caminho relativo, lembrando que a `Dockerfile` está em `./docker/todo-app/tests/Dockerfile`);
- inicie os testes com o comando `npm test`.

<details>
  <summary>➕ Informações adicionais</summary><br />

- Nesse contexto, deve-se criar um arquivo [`Dockerfile`](https://docs.docker.com/engine/reference/builder/#format) na pasta `./docker/todo-app/back-end/`, que será utilizado com comando exigido no requisito;
- Esse arquivo deve buscar reproduzir as etapas de `testes` contidas no [`README.md`](docker/todo-app/README.md) da *pseudo-aplicação* (também estão descritas na seção `O que será testado`, do requisito) para que ele rode corretamente;
- O avaliador executará o comando no arquivo `command11.dc`.

#### Dicas

- O [comando `ADD`](https://docs.docker.com/engine/reference/builder/#add) do Dockerfile, também pode ser utilizado para descompactar arquivos dentro do container.
  - Entenda a diferença entre o comando `ADD` e `COPY` [neste artigo](https://coderarena.com.br/posts/docker-tips-01-qual-e-a-diferenca-entre-add-e-copy/).
#### Observações técnicas

- A aplicação `todotests` só funciona corretamente se estiver dockerizada e dentro de uma rede docker configurada corretamente.

#### O que será testado

- Se existe um arquivo `Dockerfile` em `./docker/todo-app/tests/`:
  - O Dockerfile deve rodar a imagem `mjgargani/puppeteer:trybe1.0` para que os testes funcionem;
  - Deve adicionar o arquivo `node_modules.tar.gz` a imagem;
  - Deve copiar todos os arquivos da pasta `tests` para a imagem;
  - Ao iniciar a imagem deve rodar o comando `npm test`;
- Se ao *buildar* o Dockerfile o nome da imagem gerada é igual a `todotests`.

</details>

# Requisito bônus do projeto

## Docker-compose

### 12. Suba uma orquestração em segundo plano com o docker-compose de forma que `backend`, `frontend` e `tests` consigam se comunicar

<details>
  <summary>➕ Informações adicionais</summary><br />

O avaliador executará o comando no arquivo `command12.dc`. Este comando pressupõe a existência do arquivo `./docker/docker-compose.yml`.

O `docker-compose` deve rodar na versão 3 ou superior.

#### Dicas

- Use as imagens já **"buildadas"** que foram executadas nos requisitos 9, 10 e 11 para a criação do compose;
- Consulte a documentação em `./docker/todo-app/README.md`;
- É possível adicionar e extrair arquivos `.tar.gz` no `Dockerfile` com apenas um comando.

#### O que será testado

##### tests

- O container de `todotests` deve ter como dependencia os containers `frontend` e `backend`;
- O nome do _service_ deverá ser `todotests`;
- Deve ter uma variável de ambiente `FRONT_HOST` que recebe como valor o nome do container do `frontend`
  - Lembrando que, dentro de uma rede docker, o host de um container é identificado pelo seu nome.

##### front-end

- O container de `todofrontend` deve rodar na porta `3000`;
- O nome do _service_ deverá ser `todofront`;
- Deve ter como dependencia o container `backend`;
- Deve ter uma variável de ambiente `REACT_APP_API_HOST` que recebe como valor o nome do container do `backend`.
  - Lembrando que, dentro de uma rede docker, o host de um container é identificado pelo seu nome.

##### back-end

- O container de `todobackend` deve rodar na porta `3001`;
- O nome do _service_ deverá ser `todoback`;

</details>
