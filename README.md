<h1 align="center">
   IMERSÃO FULL CYCLE 3.0
</h1>

<h3 align="center">
	🚧  BACKEND, FRONTEND E MICRO-SERVIÇOS...  🚧
</h3>

![Imersão Full Stack && Full Cycle](https://events-fullcycle.s3.amazonaws.com/events-fullcycle/static/site/img/grupo_4417.png)

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

## Alterações no `Dockerfile - Go`:

Vamos atualizar a versão do `Go` para a `golang:1.19`, desta forma os pacotes instalados serão compatíveis entre eles.

Ao configura o `Dockerfile` com a instalação do `cobra` que vamos utilizar mais a frente no curso, mas há uma alteração a ser feita na instalação desta ferramenta como abaixo:

Precisamos substituir e incluir o comando de instalação do `cobra-cli`:

```bash
    $ go get github.com/spf13/cobra-cli@v1.3.0 && \

```

Após realizar as alterações acima o `Dockerfile` ficará da seguinte forma:

```bash
    FROM golang:1.19

    WORKDIR /go/src
    ENV PATH="/go/bin:${PATH}"
    ENV GO111MODULE=on
    ENV CGO_ENABLED=1

    RUN apt-get update && \
        apt-get install build-essential protobuf-compiler librdkafka-dev -y && \
        go install google.golang.org/grpc/cmd/protoc-gen-go-grpc@v1.3.0 && \
        go install google.golang.org/protobuf/cmd/protoc-gen-go@v1.31.0 && \
        go install github.com/spf13/cobra-cli@v1.3.0 && \
        wget https://github.com/ktr0731/evans/releases/download/0.9.1/evans_linux_amd64.tar.gz && \
        tar -xzvf evans_linux_amd64.tar.gz && \
        mv evans ../bin && rm -f evans_linux_amd64.tar.gz

    CMD ["tail", "-f", "/dev/null"]
```

Dentro do arquivo `go.mod` apague todo o conteúdo de `require` e no terminal rode o comando abaixo para instalar todas as depêndencias:

```bash
   $ go mod init
```

Observação: Com isso a aplicação deve funcionar corretamente.

## Serviços utilizados ao executar o docker-compose

- Aplicação principal
- Postgres
- PgAdmin
- Apache Kafka
- Criador dos tópicos a serem utilizados pelo Kafka
- Confluent control center
- ZooKeeper

## Como executar cobra-cli

Como explicado acima, precisamos incluir o `cobra-cli` nas instalações internas do `container`, por isso o comando para iniciar o `cobra` será: `cobra-cli init`

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
