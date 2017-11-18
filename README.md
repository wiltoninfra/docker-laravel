
# DOCKER AMBIENTE DE DESENVOLVIMENTO LARAVEL 5 #
## Serviços PHP 7.1.11 /  Nginx 1.13.x + Phpmyadmin + Mysql-Server 5.7 + Redis + MongoDB

Este script foi criado principalmente para rodar em ambientes Windows com VirtualBox, mas funciona normlamente em outras plataformas

### Padronização ###

Criamos uma estrutura de pastas a fim de facilitar o entendimento e desenvolvimento local utilizando docker:

| Pasta | Descrição |
| ------ | ------ |
| db |  Onde constam os arquivos de banco de dados do MySQL, para que ao subir as instâncias |
| dev | Pasta com os arquivos de desenvolvimento local dos arquivos clone do Git |
| infra | Itens de configuração do dos serviços, como PHP.INI, VHOSTS e LOGS|
| useful | Arquivos de Test e outros ajuda a mater a organização --LIXO-- |



## Pacotes Instalados no Windows #####
 ---------------------------------
#### 1 - Git SCM for Windows
###### Pode ser baixado no link abaixo:
https://git-scm.com/download/win
### 2 - VirtualBox
###### Pode ser baixado no link abaixo:
https://www.virtualbox.org/wiki/Downloads
### 3 - Docker ToolBox 
###### Pode ser baixado no link abaixo:
https://www.docker.com/products/docker-toolbox
### 4 - IDE's e Editores para Desenvolvimento 
###### Abaixo colocamos uma lista com algumas IDE's mas cada desenvolvedor por usar uma de sua preferência.
- PHP STORM - https://www.jetbrains.com/phpstorm/
- NETBEANS - https://netbeans.org/downloads/
- ATOM - https://atom.io/
- SUBLIME - https://www.sublimetext.com/

> **Note:**
> Todos os pacotes devem ser da versão mais atualizada.
>Os aplicativos devem ser instalados na ordem conforme apresentação acima (1,2,3), isso ajuda na associação automatica das ferramentas durante a instalação.


## Preparando o Ambiente para Desenvolvimento #####

Após a instalação do Docker estiver concluída.

Selecione uma pasta dentro do perfil de usuário:

Execute o "Docker Quickstart Terminal "
O terminal ira abrir utilizando Bash MINGW64.
Execute os comandos abaixo:

``` sh
$ pwd
> /c/Users/nomedousuario
$ _
### O temrinal deve ficar sempre com nomedousuario@nomedocomputador MINGW64 ~
### O sinal de Til (~) no final significa que esta navegando dentro do perfil do usuário
$ _
$ git clone https://meuprojetono.git MeuProjetoDocker
$ cd MeuProjetoDocker
$ docker-compose up -d --build
```

> **Note:**
Para ambientes Windows é necessário verificar qual ip da rede local esta atribuido no via Kitematic ou Docker Tools.


Após terminar o Build realize os testes e veja se seu ambiente esta funcionando.


## Instalando Laravel

Abra o console do docker e execute o comando abaixo na pasta raiz do docker

``` sh
docker exec -it comandos composer create-project --prefer-dist laravel/laravel /var/www/html/app && cd /var/www/html/app && composer update && composer install && composer dump
```

> **Note:**
Seu laravel esta pronto para uso seu repositório de arquivos na pasta DEV.
Para executar os comandos acesse o conteiner comandos.

``` sh
docker exec -it comandos /bin/bash

```
Você ira acessar o servidor linux com todos os comandos já instalados.

