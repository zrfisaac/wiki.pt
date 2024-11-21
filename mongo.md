# MongoDB

Este guia fornece informações abrangentes sobre como trabalhar com o MongoDB, incluindo operações comuns, melhores práticas e dicas para gerenciar seu banco de dados NoSQL. Se você é iniciante ou um usuário experiente, este guia ajudará você a aproveitar ao máximo o MongoDB.

## Índice

- [Introdução ao MongoDB](#introdução-ao-mongodb)  
  Visão geral do MongoDB, seus recursos e como configurá-lo.

- [Conectando ao MongoDB](#conectando-ao-mongodb)  
  Como conectar ao MongoDB usando diversos métodos.

- [Operações Básicas no MongoDB](#operações-básicas-no-mongodb)  
  Operações comuns do MongoDB, como operações CRUD (Criar, Ler, Atualizar, Excluir).

- [Consultas Avançadas no MongoDB](#consultas-avançadas-no-mongodb)  
  Consultas complexas como agregação, indexação e filtros avançados.

- [Otimização de Performance](#otimização-de-performance)  
  Dicas e melhores práticas para otimizar a performance do MongoDB.

- [Tratamento de Erros e Depuração](#tratamento-de-erros-e-depuração)  
  Como tratar erros e depurar consultas no MongoDB.

---

## Introdução ao MongoDB

MongoDB é um sistema de banco de dados NoSQL popular que armazena dados em documentos flexíveis, semelhantes ao JSON. Diferente dos bancos de dados relacionais tradicionais, o MongoDB permite que você armazene dados sem exigir um esquema pré-definido, tornando-o ideal para aplicativos que necessitam de escalabilidade e flexibilidade.

### Principais Características do MongoDB:
- Design sem esquema: Armazene dados em documentos flexíveis que podem mudar ao longo do tempo.
- Escalabilidade horizontal: Escale facilmente os aplicativos distribuindo dados entre vários servidores.
- Ricas capacidades de consulta: Suporte a indexação, agregação e análise em tempo real.
- Indexação geoespacial: Gerencie e consulte dados baseados em localização.
- Replicação e alta disponibilidade integradas com conjuntos de réplicas.
- Arquitetura distribuída com particionamento automático (sharding) para grandes implantações.

---

## Conectando ao MongoDB

Você pode conectar ao MongoDB de várias maneiras, dependendo do ambiente e da linguagem de programação que você está usando. Abaixo estão exemplos para diferentes ferramentas e linguagens.

### Exemplo usando **Mongo Shell**:

1. Abra seu terminal ou prompt de comando.
2. Execute o seguinte comando para conectar ao MongoDB:

   ```bash
   mongo --host <host> --port <porta> -u <usuário> -p <senha> --authenticationDatabase <db_autenticação>
   ```

3. Após a conexão, você pode executar comandos do MongoDB diretamente no shell.

### Exemplo usando **Node.js** com Mongoose:

```javascript
const mongoose = require('mongoose');

mongoose.connect('mongodb://<usuário>:<senha>@<host>:<porta>/<banco_de_dados>', {
  useNewUrlParser: true,
  useUnifiedTopology: true
}).then(() => {
  console.log('Conectado ao MongoDB');
}).catch(err => {
  console.error('Erro ao conectar ao MongoDB', err);
});
```

### Exemplo usando **MongoDB Compass**:

1. Abra o MongoDB Compass e clique em "Nova Conexão".
2. Insira os detalhes de conexão, como host, porta e informações de autenticação.
3. Depois de conectar, você pode visualizar suas coleções e executar consultas usando a interface gráfica.

---

## Operações Básicas no MongoDB

Aqui estão algumas operações comuns do MongoDB que você usará frequentemente.

### Inserindo Documentos
Para inserir um novo documento em uma coleção:

```javascript
db.collection('funcionarios').insertOne({
  nome: 'João Silva',
  cargo: 'Engenheiro de Software',
  salario: 75000
});
```

### Recuperando Documentos
Para recuperar todos os documentos de uma coleção:

```javascript
db.collection('funcionarios').find();
```

Para recuperar documentos com uma condição específica:

```javascript
db.collection('funcionarios').find({ cargo: 'Engenheiro de Software' });
```

### Atualizando Documentos
Para atualizar um documento na coleção:

```javascript
db.collection('funcionarios').updateOne(
  { nome: 'João Silva' },
  { $set: { salario: 80000 } }
);
```

### Deletando Documentos
Para excluir um documento de uma coleção:

```javascript
db.collection('funcionarios').deleteOne({ nome: 'João Silva' });
```

---

## Consultas Avançadas no MongoDB

O MongoDB suporta consultas complexas, incluindo agregação, indexação e filtros.

### Framework de Agregação
O framework de agregação do MongoDB permite que você realize transformações de dados complexas.

Exemplo de uso de agregação para agrupar dados:

```javascript
db.collection('funcionarios').aggregate([
  { $group: { _id: "$cargo", salarioTotal: { $sum: "$salario" } } }
]);
```

### Indexação
Índices ajudam a melhorar o desempenho das operações de leitura.

Crie um índice no campo `nome`:

```javascript
db.collection('funcionarios').createIndex({ nome: 1 });
```

### Projeção
Você pode limitar os campos retornados por uma consulta usando projeções.

```javascript
db.collection('funcionarios').find({}, { nome: 1, cargo: 1 });
```

### Ordenação
Ordene os documentos com base em um campo específico.

```javascript
db.collection('funcionarios').find().sort({ salario: -1 });
```

---

## Otimização de Performance

Aqui estão algumas dicas para otimizar a performance do MongoDB:

- **Use Índices**: Crie índices nos campos que são frequentemente usados nas consultas para acelerar a recuperação de dados.

```javascript
db.collection('funcionarios').createIndex({ cargo: 1 });
```

- **Sharding**: Distribua dados entre vários servidores para lidar com grandes conjuntos de dados de forma eficiente.

- **Use o Pipeline de Agregação**: Operações de agregação são mais eficientes do que o processamento manual no código da sua aplicação.

- **Otimize as Consultas**: Certifique-se de que suas consultas estão usando campos indexados e minimize o número de documentos retornados.

---

## Tratamento de Erros e Depuração

O MongoDB fornece várias ferramentas para ajudá-lo a tratar erros e depurar suas consultas.

### Tratando Erros no Node.js:

```javascript
db.collection('funcionarios').insertOne(dados)
  .catch(err => {
    console.error('Erro ao inserir documento:', err);
  });
```

### Usando o Plano de Explicação para Analisar Consultas:

O método `explain()` retorna informações sobre como o MongoDB executa uma consulta, ajudando a identificar gargalos de desempenho.

```javascript
db.collection('funcionarios').find().explain('executionStats');
```

Isso lhe dará informações sobre o desempenho da consulta, como se ela usou um índice.

### Habilitando o Profiler:

O profiler do MongoDB rastreia consultas lentas, permitindo que você identifique operações ineficientes.

```javascript
db.setProfilingLevel(2);
```

Para visualizar consultas lentas:

```javascript
db.system.profile.find();
```

