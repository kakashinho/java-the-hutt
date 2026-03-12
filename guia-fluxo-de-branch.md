# 🚀 Guia de Contribuição e Fluxo de Branches (Git Flow)

Este guia explica como **clonar o projeto, configurar o Git Flow e desenvolver novas funcionalidades** seguindo o fluxo padrão utilizado no repositório.

---

## 📌 Boas práticas
- ✔ Sempre atualizar a develop antes de iniciar uma feature
- ✔ Usar nomes claros para branches
- ✔ Seguir padrões de commits e bem descritivos
- ✔ Nunca desenvolver diretamente na main


# 📥 Clonando o repositório

Primeiro, clone o projeto para sua máquina, que pode ser:

- **ou** `git clone https://github.com/fatec-api/java-the-hutt.git`
- **ou** `git clone https://github.com/fatec-api/api-3dsm-frontend.git`
- **ou** `git clone https://github.com/fatec-api/api-3dsm-backend.git`


Abra a pasta:
- **ou** `cd java-the-hutt`
- **ou** `cd api-3dsm-frontend`
- **ou** `cd api-3dsm-backend`


# ⚙️ Inicializando o Git Flow
O projeto utiliza Git Flow para organizar o desenvolvimento. Aceitar tudo automaticamente com -d:
```bash
git flow init -d
```
# 🌿 Visualizando as branches
Para listar todas as branches locais e remotas:
```bash
git branch -a
```
Exemplo de saída:
```bash
* develop
  main
  remotes/origin/feature
```

# 🔄 Atualizando seu repositório local
Antes de começar qualquer trabalho, atualize o projeto.
```bash
git fetch
```
## Atualizar a branch develop:
```bash
git checkout develop
git pull origin develop
```
## Atualizar a branch main:
```bash
git checkout main
git pull origin main
```

# ✨ Criando uma nova funcionalidade (Feature)
```bash
git flow feature start nome-da-funcionalidade
```

# 💾 Salvando alterações (Commit)
```bash
git add . && git commit -m "feat: adiciona funcionalidade de busca de produtos"
```

# 📜 Visualizando histórico de commits
Para ver um resumo dos commits:
```bash
git log --oneline
```

Exemplo:
```bash
a3c9f21 feat: adiciona busca de produtos
8d12c7a fix: corrige erro de login
1a92d3f docs: atualiza documentação
```

# 🔍 Visualizando versões anteriores do código
Para visualizar o estado do projeto em um commit específico:
```bash
git checkout ID_DO_COMMIT
```

Exemplo:
```bash
git checkout a3c9f21
```

## ⚠️ Isso coloca o repositório em detached HEAD.
Para voltar à branch normal:
```bash
git checkout nome-da-branch
```

# ☁️ Enviando sua feature para o repositório remoto
```bash
git push origin feature/nome-da-funcionalidade
```

Depois disso:
Aguarde a revisão da equipe

# 🧪 Testando o merge localmente
Caso queira testar o merge antes de finalizar a branch:
Ir para a branch principal:
```bash
git checkout main
```
Criar uma branch de teste apartir da main:
```bash
git checkout -b main-teste-funcionalidade
```
Fazer merge da sua feature:
```bash
git merge feature/nome-da-funcionalidade
```

# ✅ Finalizando a feature
Após aprovação ou finalização da funcionalidade:
```bash
git flow feature finish nome-da-funcionalidade
```

# 🗑️ Deletando branches
Apagar uma branch local
```bash
git branch -D nome-da-branch
```

# ✏️ Renomeando uma branch
Para renomear uma branch local:
```bash
git branch -m feature/nome-antigo feature/nome-novo
```

# 📊 Exemplo de fluxo completo
```bash
develop (git pull origin develop)
   │
   └── feature/login (git flow feature start nome-da-funcionalidade)
            │
            └── commits (git add . && git commit -m "")
                     │
                     └── push (git push origin feature/nome-da-funcionalidade)
                             │
                             └── testando o merge localmente (git checkout -b main-teste-funcionalidade)
                                     │
                                     └── após o review (git flow feature finish nome-da-funcionalidade)
                                               │
                                               └── resolva os conflitos do merge entre a fucnionalidade e a develop

```

