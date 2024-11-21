# Git

Bem-vindo à **Wiki Git**! Este é o seu recurso completo para aprender e dominar o Git, o poderoso sistema de controle de versão usado por desenvolvedores ao redor do mundo para colaborar e gerenciar código de forma eficiente.

## Descrição

Git é um sistema de controle de versão distribuído que permite aos desenvolvedores acompanhar as alterações no código, colaborar com outros e manter a integridade dos projetos. É amplamente adotado em projetos de código aberto, fluxos de trabalho de desenvolvimento profissional e projetos pessoais de codificação.

Esta wiki cobre o básico do Git, seus comandos, dicas de fluxo de trabalho e exemplos práticos para começar a usar a ferramenta.

## Links Úteis

- [Documentação Oficial do Git](https://git-scm.com/doc)
- [GitHub Learning Lab](https://lab.github.com/)
- [Livro Pro Git (Grátis)](https://git-scm.com/book/pt-br/v2)
- [Git Cheat Sheet](https://education.github.com/git-cheat-sheet-education.pdf)
- [Tutorial GitHub Git](https://docs.github.com/pt/get-started/using-git/about-git)

## Índice

- [Descrição](#descrição)
- [Links Úteis](#links-úteis)
- [Versões do Git](#versões-do-git)
- [Comandos Básicos do Git](#comandos-básicos-do-git)

## Versões do Git

Aqui estão alguns marcos importantes na evolução do Git:

- **2005**  
  Git foi criado por Linus Torvalds para gerenciar o desenvolvimento do kernel do Linux.

- **Git 1.x (2005-2010)**  
  Introduziu a funcionalidade central, incluindo ramificação e mesclagem.

- **Git 2.x (2013)**  
  Adicionou melhorias de desempenho, melhores algoritmos para mesclagem e suporte para repositórios grandes.

- **Versões Recentes**  
  Atualizações contínuas incluem melhorias de segurança, novos recursos e melhor integração com pipelines modernos de CI/CD.

Para um histórico detalhado, visite as [Notas de Lançamento do Git](https://github.com/git/git/tree/master/Documentation/RelNotes).

## Comandos Básicos do Git

Aqui estão alguns comandos Git comuns com exemplos para ajudá-lo a começar:

**Inicializar um Repositório**  
```bash
git init
```

**Clonar um Repositório**  
```bash
git clone <url_do_repositório>
```

**Verificar o Status do Repositório**  
```bash
git status
```

**Adicionar Arquivos à Área de Staging**  
```bash
git add <nome_do_arquivo>
# Ou adicionar todas as alterações
git add .
```

**Fazer um Commit das Alterações**  
```bash
git commit -m "Mensagem do commit descrevendo as alterações"
```

**Enviar Alterações para um Repositório Remoto**  
```bash
git push origin <nome_da_branch>
```

**Puxar Alterações de um Repositório Remoto**  
```bash
git pull origin <nome_da_branch>
```

**Criar uma Nova Branch**  
```bash
git branch <nome_da_nova_branch>
```

**Alternar para uma Branch**  
```bash
git checkout <nome_da_branch>
```

**Mesclar Branches**  
```bash
git merge <nome_da_branch>
```

**Visualizar o Histórico de Commits**  
```bash
git log
```

**Desfazer Alterações**  
```bash
git reset --soft HEAD~1  # Desfaz o último commit, mantendo as alterações na área de staging
git reset --hard         # Desfaz o último commit e descarta as alterações
```

