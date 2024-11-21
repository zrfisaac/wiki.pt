# Kafka

O Apache Kafka é uma plataforma distribuída de streaming, que permite a publicação, assinatura, armazenamento e processamento de fluxos de dados em tempo real. Ele é amplamente utilizado para construir sistemas de mensagens de alta performance e escaláveis. O Kafka é frequentemente usado para monitoramento, análise de logs, processamento de eventos e muitos outros casos de uso em tempo real.

Este guia fornece uma introdução ao Kafka, incluindo exemplos em Python para demonstrar como configurar e usar o Kafka para tarefas de envio e recebimento de mensagens.

---

## Índice

- [Pré-requisitos](#pré-requisitos)  
  Instalação e configuração do Kafka e Python.

- [Conceitos Básicos](#conceitos-básicos)  
  Visão geral dos conceitos principais do Kafka, como produtores, consumidores e tópicos.

- [Exemplo de Kafka em Python](#exemplo-de-kafka-em-python)  
  Exemplo de código para enviar e receber mensagens usando Kafka em Python.

- [Conceitos Avançados de Kafka](#conceitos-avançados-de-kafka)  
  Informações sobre particionamento, tópicos, offsets e processamento de mensagens.

---

## Pré-requisitos

Para começar a trabalhar com Kafka e Python, você precisará:

- **Instalar o Kafka**: 
  Você pode seguir a documentação oficial para instalar o Apache Kafka em sua máquina ou usar um serviço de Kafka hospedado, como o Confluent Cloud.

  Instalação do Apache Kafka:
  1. Baixe e extraia o Apache Kafka em [Apache Kafka Download](https://kafka.apache.org/downloads).
  2. Inicie o Zookeeper (necessário para o Kafka):
     ```bash
     bin/zookeeper-server-start.sh config/zookeeper.properties
     ```
  3. Em seguida, inicie o Kafka:
     ```bash
     bin/kafka-server-start.sh config/server.properties
     ```

- **Biblioteca Kafka-Python**: O Kafka-Python é uma biblioteca que fornece uma interface para interagir com o Kafka usando Python. Instale-a com o seguinte comando:
  ```bash
  pip install kafka-python
  ```

---

## Conceitos Básicos

- **Produtor**: O produtor é responsável por enviar mensagens para um tópico Kafka.
- **Consumidor**: O consumidor é responsável por ler mensagens de um ou mais tópicos Kafka.
- **Tópico**: O tópico é um canal de comunicação, onde as mensagens são enviadas pelos produtores e consumidas pelos consumidores.
- **Partição**: Kafka divide cada tópico em partições, que permitem a distribuição de dados de forma paralela e escalável.
- **Offset**: O offset é o identificador de uma mensagem dentro de uma partição. O consumidor utiliza o offset para acompanhar as mensagens processadas.

---

## Exemplo de Kafka em Python

Abaixo está um exemplo simples onde mostramos como configurar um produtor e um consumidor Kafka utilizando a biblioteca Kafka-Python.

### Produtor (Enviando Mensagens)

```python
from kafka import KafkaProducer

# Conectar ao servidor Kafka
producer = KafkaProducer(bootstrap_servers='localhost:9092')

# Enviar uma mensagem para o tópico 'test'
producer.send('test', b'Hello, Kafka!')

# Esperar até que todas as mensagens sejam enviadas
producer.flush()

print("Mensagem enviada com sucesso!")

# Fechar o produtor
producer.close()
```

Neste exemplo:
- Criamos um produtor Kafka conectando ao servidor em `localhost:9092`.
- Enviamos uma mensagem simples (`b'Hello, Kafka!'`) para o tópico `test`.
- Usamos `flush()` para garantir que todas as mensagens sejam enviadas antes de fechar a conexão.

### Consumidor (Recebendo Mensagens)

```python
from kafka import KafkaConsumer

# Conectar ao servidor Kafka
consumer = KafkaConsumer('test', bootstrap_servers='localhost:9092')

# Consumir mensagens
for message in consumer:
    print(f"Mensagem recebida: {message.value.decode('utf-8')}")

# Fechar o consumidor
consumer.close()
```

Neste exemplo:
- Criamos um consumidor Kafka para o tópico `test` conectando ao servidor em `localhost:9092`.
- O consumidor escuta continuamente as mensagens do tópico e imprime as mensagens recebidas.
- O loop irá continuar até que o consumidor seja fechado.

---

## Conceitos Avançados de Kafka

### Particionamento
Os tópicos no Kafka podem ser particionados para melhorar o desempenho e a escalabilidade. Cada partição é tratada por diferentes consumidores, permitindo paralelismo e balanceamento de carga. Para produzir ou consumir mensagens de uma partição específica, o Kafka utiliza o conceito de **chaves de particionamento**.

Exemplo de envio de mensagens para partições específicas:

```python
# Enviar uma mensagem com uma chave específica, que pode ser usada para determinar a partição
producer.send('test', key=b'key1', value=b'Hello, Kafka!')
```

### Consumidor com Offsets

No Kafka, cada consumidor mantém o **offset** das mensagens que leu. Ele pode ler a partir de um offset específico ou processar as mensagens na ordem em que são recebidas. Por padrão, o Kafka armazena o offset de cada consumidor de forma automática, mas você também pode controlá-lo manualmente.

Exemplo de controle manual de offset:

```python
consumer = KafkaConsumer('test', 
                         bootstrap_servers='localhost:9092',
                         enable_auto_commit=False)

for message in consumer:
    print(f"Mensagem recebida: {message.value.decode('utf-8')}")
    
    # Confirmar manualmente o offset
    consumer.commit()
```

### Processamento de Fluxo com Kafka Streams

Kafka Streams é uma biblioteca que permite o processamento de dados em tempo real. Você pode combinar, filtrar e transformar mensagens de fluxo de dados diretamente no Kafka.

Para usar Kafka Streams com Python, você pode integrar o Kafka com outras bibliotecas de processamento de fluxo, como Apache Flink ou Apache Spark.
