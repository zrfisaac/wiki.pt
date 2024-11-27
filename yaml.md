# YAML

YAML (YAML Ain't Markup Language) é um formato de serialização de dados legível por humanos, utilizado para arquivos de configuração, armazenamento de dados e troca de dados entre sistemas. É conhecido por sua simplicidade, facilidade de uso e legibilidade, tornando-se uma escolha popular para aplicações que exigem uma representação clara e concisa de dados.

## Índice

---

### Exemplo

```yaml
metadata:
  file_name: exemplo.yaml
  version: 1.0
  created_at: "2024-11-27T15:45:00Z"
  is_active: true
  tags:
    - yaml
    - exemplo
    - dados
    - teste

user:
  id: 12345
  name: João Silva
  email: joaosilva@exemplo.com
  profile_picture:
    type: base64
    data: "iVBORw0KGgoAAAANSUhEUgAAAAUA"
  settings:
    theme: escuro
    notifications_enabled: true
    volume_level: 0.75

data_collection:
  - type: temperatura
    unit: Celsius
    value: 23.4
    timestamp: "2024-11-27T10:00:00Z"
  - type: umidade
    unit: "%"
    value: 65
    timestamp: "2024-11-27T10:00:00Z"

complex_data:
  matrix:
    - [1, 2, 3]
    - [4, 5, 6]
    - [7, 8, 9]
  records:
    - id: a1b2c3
      value: 45.67
      description: Registro exemplo 1
    - id: d4e5f6
      value: 78.9
      description: Registro exemplo 2

free_text: |
  Este é um exemplo de uma entrada de texto longo. Pode incluir várias linhas,
  caracteres especiais como !@#$%^&*(), e até Unicode como emojis 😊🌟.

additional_properties:
  nullable_field: null
  boolean_values:
    - true
    - false
    - true
  float_array:
    - 1.1
    - 2.2
    - 3.3
  nested_object:
    key1: valor1
    key2: 2
    key3:
      subkey1:
        - 1
        - 2
        - 3
      subkey2: valor aninhado
```
