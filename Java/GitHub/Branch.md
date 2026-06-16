# O que é uma Branch?

Uma **branch** é uma **linha paralela de desenvolvimento do projeto**.

Ela permite que você trabalhe em algo **sem alterar o código principal**.

Imagine o projeto como uma linha do tempo:

```
main
  |
  o---o---o
```

Agora criamos uma nova branch chamada `feature-imc`:

```
main
  |
  o---o---o
           \\
            o---o  feature-imc
```

Agora podemos:

- criar arquivos
- modificar código
- testar funcionalidades

Tudo isso **sem afetar a branch principal**.

-------- 
# Por que usar Branches?

Branches são utilizadas para:

- novas funcionalidades
- correção de bugs
- testes
- refatorações

Exemplos de nomes de branches:

```
feature-login
feature-calculo-imc
bugfix-navbar
style-header
```

Esse padrão ajuda a organizar o projeto.

---
# Como ver as branches do projeto

Para ver todas as branches:

```bash
git branch
```

Exemplo de saída:

```
* main
```

O `*` indica **em qual branch você está trabalhando**.

----
# Criando uma nova Branch

Para criar uma nova branch:

```bash
git branch nome-da-branch
```

Exemplo:

```bash
git branch feature-water
```

Isso cria a branch, mas **você ainda continua na main**.

----
# Mudando de Branch

Para trocar de branch:

```bash
git checkout nome-da-branch
```

Exemplo:

```bash
git checkout feature-water
```

Agora você está trabalhando nessa branch.

----
# Criando e mudando de Branch ao mesmo tempo

Forma mais comum usada pelos desenvolvedores:

```bash
git checkout -b nome-da-branch
```

Exemplo:

```bash
git checkout -b feature-navbar
```

Isso:

- cria a branch
- muda para ela automaticamente
----
# Trabalhando em uma Branch

Depois de criar a branch, você trabalha normalmente.

Fluxo:

```bash
git add .
git commit -m "feat: adiciona melhoria na navbar"
```

Esses commits ficam **apenas nessa branch**.

----
# Enviando a Branch para o GitHub

Para enviar a branch para o GitHub:

```bash
git push origin nome-da-branch
```

Exemplo:

```bash
git push origin fox
```

Agora a branch aparece no GitHub.

----

## Enviando para o *MAIN*
```
git switch main
```

```
git pull origin main
```

```
git merge fox
```

```
git push origin main
```