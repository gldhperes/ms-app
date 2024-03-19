# ms-escrita

## Criando Dockerfile:


## RabbitMQ:

Para rodar a imagem de RabbitMQ localmente use o seguinte comando:

...
docker run --hostname rabbit --name rabbit -p 8080:15672 -p 5672:5672 -e RABBITMQ_DEFAULT_USER=user -e RABBITMQ_DEFAULT_PASS=password rabbitmq:3-management
...

## MS-ESCRITA

Para rodar a imagem de ms-escrita.py execute o comando:

...
docker run -e "RABBITMQ_URL=host.docker.internal" <ID_DA_IMAGEM>
...

Note que no arquivo .env a variavel *RABBITMQ_URL* esta como *localhost*, para o docker  entender que se trata de um localhost, deve ser passado como parametro para a *RABBITMQ_URL* o valor de *host.docker.internal*

## kubernetes

#### Pod Name Enviroment Variable

...
    env:
        - name: APP_NAME
        valueFrom:
            fieldRef:
                fieldPath: metadata.name
 ...