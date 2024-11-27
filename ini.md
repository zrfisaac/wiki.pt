# INI

INI (Initialization File) é um formato de arquivo simples e em texto puro utilizado para configurações de software. Ele é composto por seções, cada uma contendo pares de chave-valor, o que facilita a organização e o gerenciamento de dados de configuração.

## Índice

---

### Exemplo

```ini
[metadata]
file_name = exemplo.ini
version = 1.0
created_at = 2024-11-27T15:45:00Z
is_active = true
tags = yaml, exemplo, dados, teste

[user]
id = 12345
name = João Silva
email = joaosilva@exemplo.com
profile_picture_type = base64
profile_picture_data = iVBORw0KGgoAAAANSUhEUgAAAAUA
theme = escuro
notifications_enabled = true
volume_level = 0.75

[data_collection]
entry1_type = temperatura
entry1_unit = Celsius
entry1_value = 23.4
entry1_timestamp = 2024-11-27T10:00:00Z
entry2_type = umidade
entry2_unit = %
entry2_value = 65
entry2_timestamp = 2024-11-27T10:00:00Z

[complex_data]
matrix_row1 = 1, 2, 3
matrix_row2 = 4, 5, 6
matrix_row3 = 7, 8, 9
record1_id = a1b2c3
record1_value = 45.67
record1_description = Registro exemplo 1
record2_id = d4e5f6
record2_value = 78.9
record2_description = Registro exemplo 2

[free_text]
value = Este é um exemplo de uma entrada de texto longo. Pode incluir várias linhas, caracteres especiais como !@#$%^&*(), e até Unicode como emojis 😊🌟.

[additional_properties]
nullable_field = null
boolean_values = true, false, true
float_array = 1.1, 2.2, 3.3
nested_object_key1 = valor1
nested_object_key2 = 2
nested_object_subkey1 = 1, 2, 3
nested_object_subkey2 = valor aninhado
```
