# JSON

JSON (JavaScript Object Notation) é um formato leve de intercâmbio de dados que é fácil para os humanos lerem e escreverem e simples para as máquinas analisarem e gerarem. Ele é amplamente utilizado para transmitir dados entre um servidor e um cliente em aplicações web e para armazenar dados estruturados.

## Índice

---

### Exemplo

```json
{
  "metadata": {
    "nome_arquivo": "exemplo.json",
    "versao": 1.0,
    "criado_em": "2024-11-27T15:45:00Z",
    "ativo": true,
    "tags": ["json", "exemplo", "dados", "teste"]
  },
  "usuario": {
    "id": 12345,
    "nome": "João Silva",
    "email": "joaosilva@exemplo.com",
    "foto_perfil": {
      "tipo": "base64",
      "dados": "iVBORw0KGgoAAAANSUhEUgAAAAUA"
    },
    "configuracoes": {
      "tema": "escuro",
      "notificacoes_ativadas": true,
      "nivel_volume": 0.75
    }
  },
  "coleta_dados": [
    {
      "tipo": "temperatura",
      "unidade": "Celsius",
      "valor": 23.4,
      "horario": "2024-11-27T10:00:00Z"
    },
    {
      "tipo": "umidade",
      "unidade": "%",
      "valor": 65,
      "horario": "2024-11-27T10:00:00Z"
    }
  ],
  "dados_complexos": {
    "matriz": [
      [1, 2, 3],
      [4, 5, 6],
      [7, 8, 9]
    ],
    "registros": [
      {
        "id": "a1b2c3",
        "valor": 45.67,
        "descricao": "Registro exemplo 1"
      },
      {
        "id": "d4e5f6",
        "valor": 78.9,
        "descricao": "Registro exemplo 2"
      }
    ]
  },
  "texto_livre": "Este é um exemplo de uma entrada de texto longo. Pode incluir várias linhas,\ncaracteres especiais como !@#$%^&*(), e até Unicode como emojis 😊🌟.",
  "propriedades_adicionais": {
    "campo_nulo": null,
    "valores_booleanos": [true, false, true],
    "array_float": [1.1, 2.2, 3.3],
    "objeto_aninhado": {
      "chave1": "valor1",
      "chave2": 2,
      "chave3": {
        "subchave1": [1, 2, 3],
        "subchave2": "valor aninhado"
      }
    }
  }
}
```
