<h1 align="center">
   IMERSÃO FULL CYCLE 3.0
</h1>

<h3 align="center">
	🚧  BACKEND, FRONTEND E MICRO-SERVIÇOS...  🚧
</h3>

## Imagens do projeto

<p align="center">
  <a href="https://imgur.com/7ktsFje"><img src="https://i.imgur.com/7ktsFje.png" title="source: imgur.com" /></a>
  <br />
</p>

## Informações da Imersão

Participei da imersão FULL CYCLE: 
Link do curso: https://imersao.fullcycle.com.br


## Microsserviço CodePix

Esse microsserviço tem o objetivo de ser um hub de transações entre os bancos que simularemos durante o projeto.

## Executar o projeto

Utilizamos Docker para que todos os serviços que utilizaremos fiquem disponíveis e acessível para que possa rodar e ser consumido pelo serviços.

```bash	
    # Faça o clone do projeto
    $ git clone nome_do_projeto

    # Acesse a pasta do projeto
    $ cd nome_do_projeto

    # Tendo o docker instalado em sua máquina apenas execute
    $ docker compose up -d
```

## Executar a aplicação

```bash	
    # Acesse o container da aplicação executando
    $ docker exec -it codepix_app bash

    # Dentro do container, execute
    $ go run cmd/codepix/main.go
```

## Serviços utilizados ao executar o docker-compose

- Aplicação principal
- Postgres
- PgAdmin
- Apache Kafka
- Criador dos tópicos a serem utilizados pelo Kafka
- Confluent control center
- ZooKeeper

## Possíveis erros

Caso esteja recebendo algum erro de dependências do `Golang` veja este guia: [Guia de ajustes](../README.md#alterações-no-dockerfile---go)

## Créditos

- [Full Cycle](fullcycle.com.br/)

## Desenvolvedor do projeto

<a href="https://github.com/SilvaneiMartins">
    <img
        style="border-radius:50%"
        src="https://github.com/SilvaneiMartins.png"
        width="100px;"
        alt="Silvanei Martins"
    />
</a>
<br />
<a href="https://github.com/SilvaneiMartins" title="Silvanei martins" >
    <sub style="font-size: 20px; font-weight: bold">
        👨‍🚀 <b>Silvanei Martins</b>
    </sub>
</a>
<br />
🚀 Feito com muito ❤️ e carinho!
