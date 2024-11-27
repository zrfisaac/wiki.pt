# XML

**XML** (Extensible Markup Language) é uma linguagem de marcação projetada para armazenar e transportar dados em um formato que seja tanto legível por humanos quanto por máquinas. Ela é altamente flexível e permite que os usuários definam suas próprias tags, tornando-a adequada para uma ampla variedade de aplicações, incluindo armazenamento de documentos, arquivos de configuração e troca de dados entre sistemas.

## Index

---

### Example

```xml
<?xml version="1.0" encoding="UTF-8"?>
<documento>
  <metadata>
    <nome_arquivo>exemplo.xml</nome_arquivo>
    <versao>1.0</versao>
    <criado_em>2024-11-27T15:45:00Z</criado_em>
    <ativo>true</ativo>
    <tags>
      <tag>xml</tag>
      <tag>exemplo</tag>
      <tag>dados</tag>
      <tag>teste</tag>
    </tags>
  </metadata>

  <usuario>
    <id>12345</id>
    <nome>João Silva</nome>
    <email>joaosilva@exemplo.com</email>
    <foto_perfil>
      <tipo>base64</tipo>
      <dados>iVBORw0KGgoAAAANSUhEUgAAAAUA</dados>
    </foto_perfil>
    <configuracoes>
      <tema>escuro</tema>
      <notificacoes_ativadas>true</notificacoes_ativadas>
      <nivel_volume>0.75</nivel_volume>
    </configuracoes>
  </usuario>

  <coleta_dados>
    <entrada>
      <tipo>temperatura</tipo>
      <unidade>Celsius</unidade>
      <valor>23.4</valor>
      <horario>2024-11-27T10:00:00Z</horario>
    </entrada>
    <entrada>
      <tipo>umidade</tipo>
      <unidade>%</unidade>
      <valor>65</valor>
      <horario>2024-11-27T10:00:00Z</horario>
    </entrada>
  </coleta_dados>

  <dados_complexos>
    <matriz>
      <linha>1 2 3</linha>
      <linha>4 5 6</linha>
      <linha>7 8 9</linha>
    </matriz>
    <registros>
      <registro>
        <id>a1b2c3</id>
        <valor>45.67</valor>
        <descricao>Registro exemplo 1</descricao>
      </registro>
      <registro>
        <id>d4e5f6</id>
        <valor>78.9</valor>
        <descricao>Registro exemplo 2</descricao>
      </registro>
    </registros>
  </dados_complexos>

  <texto_livre>
    <![CDATA[
    Este é um exemplo de uma entrada de texto longo. Pode incluir várias linhas,
    caracteres especiais como !@#$%^&*(), e até Unicode como emojis 😊🌟.
    ]]>
  </texto_livre>

  <propriedades_adicionais>
    <campo_nulo xsi:nil="true" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" />
    <valores_booleanos>
      <valor>true</valor>
      <valor>false</valor>
      <valor>true</valor>
    </valores_booleanos>
    <array_float>
      <valor>1.1</valor>
      <valor>2.2</valor>
      <valor>3.3</valor>
    </array_float>
    <objeto_aninhado>
      <chave1>valor1</chave1>
      <chave2>2</chave2>
      <chave3>
        <subchave1>1 2 3</subchave1>
        <subchave2>valor aninhado</subchave2>
      </chave3>
    </objeto_aninhado>
  </propriedades_adicionais>
</documento>
```
