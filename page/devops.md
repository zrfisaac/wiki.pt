# 🔄 DevOps

> *Última atualização: 2025-08-28*

DevOps é uma **cultura, conjunto de práticas e ferramentas** que integra **desenvolvimento (Dev)** e **operações (Ops)** para entregar software de forma **rápida, confiável e contínua**.

* Foca em **automação**, **colaboração entre equipes** e **monitoramento constante**.
* Objetivo: reduzir erros manuais, acelerar entregas e manter a estabilidade do sistema.

```mermaid
flowchart LR
    A[1. Planeja] --> B[2. Codifica]
    B --> C[3. Build]
    C --> D[4. Testa]
    D --> E[5. Publica]
    E --> F[6. Monitora]
    F --> A[1. Planeja]

    subgraph CI/CD
        B --> C --> D --> E
    end
````

* **1. Planeja**

  Define **o que deve ser feito**: requisitos, tarefas, prioridades e backlog.

  * Ferramentas: Jira, Trello, Azure Boards.
  * Objetivo: organizar o trabalho e alinhar equipes.

* **2. Codifica**

  Os desenvolvedores escrevem o código e versionam no **repositório**.

  * Ferramentas: Git, GitHub, GitLab, Bitbucket.
  * Objetivo: manter o código centralizado e rastreável.

* **3. Build**

  O código é **compilado automaticamente**, gerando executáveis ou pacotes.

  * Ferramentas: Jenkins, GitLab CI, Azure Pipelines.
  * Objetivo: transformar o código em algo que possa ser testado ou publicado.

* **4. Testa**

  Executa **testes automatizados** para garantir qualidade.

  * Ferramentas: DUnitX (Delphi), NUnit, JUnit, Selenium.
  * Objetivo: detectar erros antes que cheguem à produção.

* **5. Publica (Deploy)**

  Entrega o software em **produção ou ambiente de homologação**.

  * Ferramentas: Octopus Deploy, Ansible, Docker, Kubernetes.
  * Objetivo: disponibilizar a versão para os usuários ou clientes.

* **6. Monitora**

  Acompanha a **saúde do sistema**: desempenho, erros e logs.

  * Ferramentas: Prometheus, Grafana, ELK Stack, New Relic.
  * Objetivo: detectar problemas e gerar feedback para melhorias.

## CI/CD

CI/CD é uma parte do DevOps que foca na **automação do fluxo de desenvolvimento**:

  * **CI (Continuous Integration / Integração Contínua)** → Cada mudança de código é **integrada, compilada e testada automaticamente**.
  * **CD (Continuous Delivery/Deployment / Entrega Contínua)** → O código aprovado é **preparado ou enviado automaticamente para produção**, reduzindo a intervenção manual.

* **Diferença entre DevOps e CI/CD**

  * **DevOps** = filosofia, cultura e conjunto de práticas para toda a entrega de software.
  * **CI/CD** = parte do DevOps, voltada para **automatizar build, testes e deploy**.

## Ferramentas

### **1. Controle de versão (Version Control)**

* Git (GitHub, GitLab, Bitbucket)
* Subversion (SVN)
* Mercurial

**Função:** manter o código centralizado, rastreável e permitir colaboração entre devs.

### **2. Integração Contínua / Entrega Contínua (CI/CD)**

* Jenkins
* GitLab CI/CD
* GitHub Actions
* Azure Pipelines
* CircleCI
* Travis CI

**Função:** automatizar build, testes e deploy do código.

### **3. Automação de Build / Empacotamento**

* Maven, Gradle (Java)
* Make, CMake (C/C++)
* DUnitX / Delphi Build Tools (Delphi)
* Docker (para empacotamento em containers)

**Função:** gerar binários, instaladores ou pacotes prontos para teste e deploy.

### **4. Configuração e Gestão de Infraestrutura**

* Ansible
* Puppet
* Chef
* Terraform
* SaltStack

**Função:** gerenciar servidores, rede, bancos de dados e infraestrutura como código.

### **5. Monitoramento e Observabilidade**

* Prometheus
* Grafana
* ELK Stack (Elasticsearch, Logstash, Kibana)
* New Relic
* Datadog

**Função:** acompanhar performance, logs e erros em produção.

### **6. Comunicação e Colaboração**

* Slack / Microsoft Teams
* Confluence
* Trello / Jira
* Notion

**Função:** manter equipes alinhadas, gerenciar tarefas e receber alertas automáticos.

### **7. Contêineres e Orquestração**

* Docker
* Kubernetes
* OpenShift

**Função:** padronizar ambientes, facilitar deploy e escalabilidade.
