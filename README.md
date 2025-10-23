# 🧩 Aula Prática – Git Local (sem GitHub)

## 🎯![ArcherGIF](https://github.com/user-attachments/assets/ba74e937-6489-47ef-8eb7-e4d0f5657bfe)
 Objetivo
Aprender a utilizar o **Git** localmente para versionar projetos, criando commits, branches e manipulando o histórico de forma segura.

---

## 🧱 1. Configuração inicial

Esses comandos configuram o nome e o e-mail do usuário (necessário para registrar os commits).

```bash
git config --global user.name "Seu Nome"
git config --global user.email "seuemail@exemplo.com"
git config --global core.editor "code --wait"   # Define o VS Code como editor padrão (opcional)
git config --list                                # Verifica as configurações atuais
```

---

## 📂 2. Criar e iniciar um repositório

```bash
mkdir meu_projeto
cd meu_projeto
git init
```

> O comando `git init` cria um repositório local, gerando a pasta oculta `.git`.

---

## 🏷️ 3. Alterar a branch padrão de `master` para `main`

Por padrão, o Git pode criar a branch inicial como **master**.  
Para padronizar e seguir boas práticas, altere para **main**:

```bash
git branch -m master main
```

Se quiser definir **main** como padrão para novos repositórios:

```bash
git config --global init.defaultBranch main
```

---

## 📄 4. Criar arquivos e verificar status

```bash
echo "Meu primeiro arquivo" > readme.txt
git status
```

> `git status` mostra arquivos novos, modificados ou prontos para commit.

---

## 🧺 5. Adicionar arquivos à área de staging

```bash
git add readme.txt       # adiciona um arquivo específico
git add .                # adiciona todos os arquivos do diretório
git status
```

> A área de staging é onde os arquivos ficam “preparados” antes do commit.

---

## 💾 6. Fazer o primeiro commit

```bash
git commit -m "Primeiro commit - adiciona readme.txt"
```

> Um commit é o “salvamento” oficial no histórico do repositório.

---

## 🔍 7. Ver histórico e detalhes

```bash
git log
git log --oneline
git show
```

> Use `--oneline` para visualizar um resumo simplificado.

---

## ✏️ 8. Editar arquivos e registrar mudanças

```bash
echo "Adicionando nova linha" >> readme.txt
git status
git diff
git add readme.txt
git commit -m "Atualiza readme.txt com nova linha"
```

> `git diff` mostra as diferenças entre a versão atual e a anterior.

---

## ♻️ 9. Desfazer mudanças

```bash
git restore readme.txt              # descarta mudanças não adicionadas
git restore --staged readme.txt     # remove da área de staging
```

> Ideal para corrigir erros antes de um commit.

---

## 🌿 10. Criar e alternar entre branches

```bash
git branch                         # lista branches
git branch nova_funcionalidade     # cria nova branch
git switch nova_funcionalidade     # muda para ela
```

> Cada branch é uma linha independente de desenvolvimento.

---

## 🧬 11. Fazer commits em outra branch

```bash
echo "Nova feature" > feature.txt
git add feature.txt
git commit -m "Adiciona nova feature"
```

---

## 🔀 12. Voltar e mesclar mudanças

```bash
git switch main
git merge nova_funcionalidade
```

> Junta as alterações da branch `nova_funcionalidade` na `main`.

---

## 🗑️ 13. Excluir branches locais

```bash
git branch -d nova_funcionalidade
```

---

## 🧹 14. Ignorar arquivos com `.gitignore`

Crie um arquivo chamado `.gitignore` e adicione:

```
*.log
*.tmp
node_modules/
```

Depois:

```bash
git add .gitignore
git commit -m "Adiciona arquivo .gitignore"
```

---

## 🧠 15. Visualizar informações úteis

```bash
git status
git log --oneline --graph --decorate
git diff
git show HEAD
```

> `--graph` mostra o histórico com ramificações visualmente.

---

## 💡 16. Exemplo de fluxo completo

```bash
git init
echo "Aula prática Git local" > readme.txt
git add .
git commit -m "Primeiro commit"
git branch dev
git switch dev
echo "Nova versão em desenvolvimento" >> readme.txt
git add .
git commit -m "Atualiza versão dev"
git switch main
git merge dev
git log --oneline --graph
```

---

## 🧬 17. Clonar um Repositório `git clone`
Quando usar: Sempre que você for começar a trabalhar em um projeto que já está hospedado online.
```bash
git clone <URL_DO_REPOSITÓRIO>
# Exemplo:
# git clone https://github.com/usuario/meu-projeto.git
cd meu-projeto
```

---

## ➕ 18. Preparar Alterações `git add`
Quando usar: Depois de fazer mudanças em seus arquivos e antes de realizar o `commit`.
```bash
# Adiciona um arquivo específico à área de staging
git add nome-do-arquivo.extensao

# Adiciona todas as alterações e novos arquivos à área de staging
git add .
```

---
## 🖨️ 19. Salvar no Histórico Local `git commit`
Quando usar: Após ter preparado todas as alterações relacionadas a uma tarefa ou correção.
```bash
git commit -m "feat: Adiciona nova tela de login"
# OU (para commits mais longos, abrirá o editor):
git commit
```
---
## 🪢 20. Enviar para o Remoto `git push`
Quando usar: Quando você finaliza uma tarefa e deseja que a equipe ou o projeto online recebam suas atualizações.
```bash
# Envia commits da sua branch local para a branch remota
git push origin <nome-da-branch>
# Exemplo, enviando para a branch principal:
# git push origin main
```
---
## 🚀 21. Fluxo de Trabalho Típico
Um ciclo de contribuição se resume a:

1. git clone (Apenas uma vez)

2. Fazer Alterações no Código

3. git add .

4. git commit -m "mensagem"

5. git push (para enviar as alterações)

---
## 💡Ferramenta Auxiliar: GitFluence (Seu Assistente de IA)
O GitFluence é uma solução online que utiliza Inteligência Artificial (IA) para simplificar a busca por comandos Git. Ele atua como um Gerador de Comandos Git em linguagem natural.

O que faz: Você digita o que deseja realizar (em português ou inglês) e a ferramenta retorna o comando Git exato, pronto para ser copiado e colado no seu terminal.

Quando usar: Quando você sabe qual ação tomar, mas esqueceu a sintaxe correta ou precisa de comandos mais complexos rapidamente.

---
## 📘 Créditos

Material criado para fins educacionais na aula prática de **Git Local**,  
ministrada por *Anderson R. M. Gomes* 🧑‍🏫

---

**🚀 Próximos passos:**  
Na próxima aula, você aprenderá a conectar este repositório local ao GitHub com os comandos `git remote`, `git push` e `git pull`.
