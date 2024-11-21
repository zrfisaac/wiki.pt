# Docker

Bem-vindo à **Wiki do Docker**! Este recurso foi projetado para ajudar desenvolvedores a entender e usar o Docker para contêinerização, automatizando a implantação de aplicativos e melhorando a eficiência do ciclo de vida do desenvolvimento.

## Descrição

O Docker é uma plataforma de código aberto usada para automatizar a implantação, escalabilidade e gerenciamento de aplicativos em contêineres. Um contêiner é um pacote independente e executável que inclui tudo o que é necessário para executar um software, incluindo código, tempo de execução, bibliotecas e dependências.

O Docker permite que os desenvolvedores construam aplicativos e serviços, os embalem com todas as dependências necessárias e os implantem de forma consistente em qualquer ambiente. É amplamente utilizado nas práticas de DevOps para criar ambientes de desenvolvimento consistentes, agilizar testes e permitir pipelines de integração contínua e entrega contínua (CI/CD).

## Links Úteis

- [Documentação Oficial do Docker](https://docs.docker.com/)
- [Repositório do Docker no GitHub](https://github.com/docker/docker)
- [Referência da CLI do Docker](https://docs.docker.com/engine/reference/commandline/)
- [Documentação do Docker Compose](https://docs.docker.com/compose/)
- [Docker Hub](https://hub.docker.com/)

## Índice

- [Descrição](#descrição)
- [Links Úteis](#links-úteis)
- [Versões do Docker](#versões-do-docker)
- [Comandos Básicos do Docker](#comandos-básicos-do-docker)

## Versões do Docker

O Docker passou por várias atualizações desde seu lançamento. Algumas versões principais incluem:

- **Docker 1.0**  
  Lançado em 2013, marcou o lançamento oficial do Docker, introduzindo recursos de contêinerização e estabelecendo o Docker como líder no espaço de tecnologias de contêiner.

- **Docker 1.12**  
  Introduziu o modo Docker Swarm, fornecendo clustering nativo e orquestração para gerenciar contêineres Docker em um ambiente distribuído.

- **Docker 18.09**  
  Adicionou melhorias significativas no suporte ao Kubernetes, rede de contêineres e gerenciamento de imagens, tornando o Docker ainda mais adequado para ambientes de produção em larga escala.

- **Docker 20.10**  
  A versão estável mais recente, proporcionando melhorias contínuas em segurança, desempenho e compatibilidade com o ecossistema Kubernetes.

Para uma lista detalhada das versões do Docker e notas de lançamento, visite o [Histórico de Versões do Docker](https://docs.docker.com/engine/release-notes/).

## Comandos Básicos do Docker

Aqui estão alguns comandos básicos do Docker para ajudar você a começar a usar o Docker:

**Instalar o Docker**  
Siga o guia de instalação na [Documentação do Docker](https://docs.docker.com/get-docker/).

**Verificar a Versão do Docker**  
```bash
docker --version
```

**Executar um Contêiner Docker**  
```bash
docker run hello-world
```
Este comando executa o contêiner oficial "hello-world", que imprime uma mensagem confirmando que o Docker está instalado corretamente.

**Listar Contêineres em Execução**  
```bash
docker ps
```
Este comando exibe todos os contêineres que estão atualmente em execução.

**Listar Todos os Contêineres (incluindo os parados)**  
```bash
docker ps -a
```

**Criar uma Imagem a partir de um Dockerfile**  
```bash
docker build -t minha-imagem .
```
Este comando cria uma imagem Docker usando o `Dockerfile` no diretório atual.

**Executar um Contêiner a partir de uma Imagem**  
```bash
docker run -d --name meu-contêiner minha-imagem
```
Isso executa um contêiner a partir da imagem `minha-imagem` no modo destacado (`-d`), nomeando-o como `meu-contêiner`.

**Parar um Contêiner em Execução**  
```bash
docker stop meu-contêiner
```

**Remover um Contêiner Parado**  
```bash
docker rm meu-contêiner
```

**Listar Imagens Docker**  
```bash
docker images
```

**Remover uma Imagem Docker**  
```bash
docker rmi minha-imagem
```

**Usando Docker Compose**  
O Docker Compose é usado para definir e gerenciar aplicativos Docker com múltiplos contêineres. Veja como você pode usá-lo:

1. Crie um arquivo `docker-compose.yml` com as definições de seus contêineres.
2. Execute `docker-compose up` para iniciar todos os contêineres definidos no arquivo Compose.

Exemplo de `docker-compose.yml`:
```yaml
version: '3'
services:
  web:
    image: nginx
    ports:
      - "8080:80"
```
Isso executa um contêiner Nginx e mapeia a porta 8080 no host para a porta 80 dentro do contêiner.

**Visualizar os Logs de um Contêiner**  
```bash
docker logs meu-contêiner
```

**Executar um Comando Interativo dentro de um Contêiner**  
```bash
docker exec -it meu-contêiner /bin/bash
```
Isso abre uma sessão de terminal interativa dentro de um contêiner em execução.
