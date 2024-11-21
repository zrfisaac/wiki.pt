# Python  

Bem-vindo à **Wiki Python**! Este é um recurso abrangente para desenvolvedores que trabalham com Python, oferecendo insights, dicas e exemplos para ajudar você a aproveitar ao máximo essa linguagem de programação versátil.  

## Descrição  

Python é uma linguagem de programação de alto nível e interpretada, conhecida por sua legibilidade e flexibilidade. É amplamente utilizada no desenvolvimento web, ciência de dados, aprendizado de máquina, automação e muito mais. Com um extenso ecossistema de bibliotecas e frameworks, o Python possibilita desenvolvimento rápido e soluções escaláveis.  

Esta wiki serve como um ponto central para explorar os recursos do Python, compreender suas capacidades e acessar recursos úteis para melhorar seus projetos.  

## Links Úteis  

- [Documentação Oficial do Python](https://docs.python.org/pt-br/3/)  
- [PyPI - Python Package Index](https://pypi.org/)  
- [Repositório Python no GitHub](https://github.com/python/cpython)  
- [Guia de Estilo Python (PEP 8)](https://peps.python.org/pep-0008/)  
- [Tutoriais Interativos de Python](https://www.learnpython.org/)  

## Índice  

- [Descrição](#descrição)  
- [Links Úteis](#links-úteis)  
- [Versões do Python](#versões-do-python)  
- [Exemplos de Código Básico](#exemplos-de-código-básico)  

## Versões do Python  

O Python evoluiu significativamente desde sua criação. Aqui estão alguns marcos importantes:  

- **Python 2.x**  
  Introduziu uma ampla gama de bibliotecas, mas foi oficialmente descontinuado em 2020.  

- **Python 3.0**  
  Lançado em 2008, trouxe melhorias significativas como suporte a Unicode e sintaxe aprimorada, quebrando a compatibilidade com o Python 2.  

- **Python 3.6**  
  Adicionou f-strings para formatação de strings e type hints para maior clareza no código.  

- **Python 3.9**  
  Introduziu operadores de união de dicionário (`|`), tipagem para tipos embutidos e outras melhorias.  

- **Python 3.11**  
  Lançado em 2022, inclui execução mais rápida e mensagens de erro aprimoradas.  

Para um histórico completo das versões do Python, visite as [Notas de Lançamento do Python](https://docs.python.org/pt-br/3/whatsnew/).  

## Exemplos de Código Básico  

Aqui estão alguns exemplos práticos para começar a programar em Python:  

**Exemplo "Olá, Mundo"**  
```python
print("Olá, Mundo!")
```

**Lendo um Arquivo**  
```python
with open("exemplo.txt", "r") as arquivo:
    conteudo = arquivo.read()
    print(conteudo)
```

**Usando um Loop For**  
```python
for i in range(5):
    print(f"Iteração {i}")
```

**Função Simples**  
```python
def saudacao(nome):
    return f"Olá, {nome}!"

print(saudacao("Alice"))
```

**Buscando Dados de uma API Web**  
```python
import requests

resposta = requests.get("https://api.github.com")
if resposta.status_code == 200:
    print("Dados da API:", resposta.json())
else:
    print("Falha ao buscar dados")
```

**Programação Orientada a Objetos Básica**  
```python
class Animal:
    def __init__(self, nome):
        self.nome = nome

    def falar(self):
        print(f"{self.nome} faz um som.")

cachorro = Animal("Cachorro")
cachorro.falar()
```

