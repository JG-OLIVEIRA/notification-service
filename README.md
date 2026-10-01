# Notification Service

## Descrição

Microservice responsável por enviar notificações de pedido por e-mail, consumindo eventos `order-placed` publicados no Apache Kafka.

## Funcionalidades

- Consumo de eventos de pedido criado
- Desserialização de eventos no formato Avro
- Integração com o Schema Registry
- Envio de e-mails de confirmação de pedido
- Monitoramento com Actuator, métricas e tracing

## Tecnologias

- **Spring Framework** — Injeção de Dependências, Beans e Configurações
- **Spring Boot** — Autoconfiguração e Actuator
- **Spring Web** — Configuração da aplicação
- **Spring Kafka** — Consumo de eventos e integração com Kafka
- **Apache Avro** — Serialização e geração de classes a partir de schema
- **Confluent Schema Registry** — Gerenciamento dos schemas dos eventos
- **Spring Mail** — Envio de notificações por SMTP
- **Micrometer, Prometheus e Zipkin** — Métricas e tracing

## Pré-requisitos

- Java Development Kit (JDK) 21 ou mais recente
- Maven
- Docker
- Apache Kafka na porta `9092`
- Schema Registry na porta `8085`
- Serviço SMTP configurado

## Execução

Configure as credenciais SMTP no arquivo `src/main/resources/application.properties` e inicie o Kafka e o Schema Registry conforme o ambiente local.

Para executar o serviço:

```bash
./mvnw spring-boot:run
```

O serviço ficará disponível na porta `8083` e consumirá eventos do tópico `order-placed`.
