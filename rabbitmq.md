# Guia RabbitMQ

O RabbitMQ é um popular broker de mensagens open-source, amplamente utilizado para facilitar a comunicação entre diferentes aplicações ou serviços. Ele é muito usado para enfileiramento de mensagens, suporta comunicação assíncrona e garante a confiabilidade na entrega das mensagens.

Este guia oferece uma introdução ao RabbitMQ com exemplos em Python para demonstrar como configurar e usar o RabbitMQ para tarefas de mensagens, como envio e recebimento de mensagens.

---

## Índice

- [Pré-requisitos](#pré-requisitos)  
  Instalação e configuração do RabbitMQ e Python.

- [Conceitos Básicos](#conceitos-básicos)  
  Visão geral dos conceitos principais do RabbitMQ, como produtores, consumidores e filas.

- [Exemplo de RabbitMQ em Python](#exemplo-de-rabbitmq-em-python)  
  Exemplo de código para enviar e receber mensagens usando RabbitMQ em Python.

- [Conceitos Avançados de RabbitMQ](#conceitos-avançados-de-rabbitmq)  
  Informações sobre filas duráveis, mensagens persistentes e roteamento.

---

## Pré-requisitos

Para começar a trabalhar com RabbitMQ e Python, você precisará instalar:

- **Servidor RabbitMQ**: O servidor RabbitMQ deve estar em execução em sua máquina ou acessível em uma rede. Você pode seguir o guia de instalação do RabbitMQ na [documentação oficial](https://www.rabbitmq.com/).
  
- **Biblioteca Pika**: Pika é uma biblioteca Python que fornece uma interface para RabbitMQ. Instale-a usando pip:
  ```bash
  pip install pika
  ```

---

## Conceitos Básicos

- **Produtor**: Um programa que envia mensagens para uma fila.
- **Consumidor**: Um programa que recupera e processa mensagens de uma fila.
- **Fila**: Um buffer que armazena mensagens até que sejam consumidas.
- **Exchange**: Roteia mensagens para a fila apropriada.

---

## Exemplo de RabbitMQ em Python

Abaixo está um exemplo simples onde demonstramos como configurar um produtor e consumidor do RabbitMQ utilizando a biblioteca Pika.

### Produtor (Enviando Mensagens)

```python
import pika

# Conectar ao servidor RabbitMQ
connection = pika.BlockingConnection(pika.ConnectionParameters('localhost'))
channel = connection.channel()

# Declarar uma fila chamada 'hello'
channel.queue_declare(queue='hello')

# Enviar uma mensagem para a fila 'hello'
channel.basic_publish(exchange='',
                      routing_key='hello',
                      body='Hello World!')

print(" [x] Enviado 'Hello World!'")

# Fechar a conexão
connection.close()
```

Neste exemplo:
- Criamos uma conexão com o servidor RabbitMQ em `localhost`.
- Declaramos uma fila chamada `hello`. Caso a fila não exista, ela será criada.
- Enviamos a mensagem `"Hello World!"` para a fila `hello` utilizando o método `basic_publish`.
- Por fim, fechamos a conexão após enviar a mensagem.

### Consumidor (Recebendo Mensagens)

```python
import pika

# Conectar ao servidor RabbitMQ
connection = pika.BlockingConnection(pika.ConnectionParameters('localhost'))
channel = connection.channel()

# Declarar uma fila chamada 'hello'
channel.queue_declare(queue='hello')

# Função de callback para processar as mensagens
def callback(ch, method, properties, body):
    print(f" [x] Recebido {body.decode()}")

# Começar a consumir mensagens da fila 'hello'
channel.basic_consume(queue='hello', on_message_callback=callback, auto_ack=True)

print(' [*] Aguardando mensagens. Para sair pressione CTRL+C')
channel.start_consuming()
```

Neste exemplo:
- Conectamos ao servidor RabbitMQ e declaramos novamente a fila `hello`.
- Definimos a função `callback`, que será chamada para processar as mensagens recebidas. Ela simplesmente imprime a mensagem recebida (`body.decode()`).
- Utilizamos o método `basic_consume` para começar a escutar as mensagens da fila `hello`. Quando uma mensagem for recebida, a função `callback` é disparada.
- `auto_ack=True` confirma automaticamente a mensagem, indicando que ela foi processada.

---

## Conceitos Avançados de RabbitMQ

### Filas Duráveis
Por padrão, as filas no RabbitMQ não são duráveis, ou seja, se o RabbitMQ falhar, todas as mensagens na fila serão perdidas. Para tornar as filas duráveis, você pode especificar o parâmetro `durable=True` ao declarar a fila.

```python
channel.queue_declare(queue='hello', durable=True)
```

### Mensagens Persistentes
Para garantir que as mensagens não sejam perdidas caso o RabbitMQ falhe, você pode torná-las persistentes, definindo a propriedade `delivery_mode=2` ao publicar a mensagem.

```python
channel.basic_publish(exchange='',
                     routing_key='hello',
                     body='Hello World!',
                     properties=pika.BasicProperties(
                         delivery_mode=2,  # Torna a mensagem persistente
                     ))
```

### Exchanges e Roteamento
O RabbitMQ suporta diferentes tipos de exchanges (direct, topic, fanout, headers) para rotear as mensagens para as filas. Você pode usar diferentes exchanges para controlar como as mensagens são roteadas.

Exemplo utilizando uma **exchange do tipo direct**:

```python
# Produtor usando uma exchange do tipo direct
channel.exchange_declare(exchange='logs', exchange_type='direct')
channel.basic_publish(exchange='logs', routing_key='info', body='Esta é uma mensagem de info')

# Consumidor usando uma exchange do tipo direct
channel.exchange_declare(exchange='logs', exchange_type='direct')
channel.queue_declare(queue='info_logs')
channel.queue_bind(exchange='logs', queue='info_logs', routing_key='info')
```
