# Dinâmica de Grupos de Trabalho

Este repositório foi estruturado para apoiar **grupos de 3 membros** que irão desenvolver funcionalidades em paralelo. Cada grupo trabalha em sua própria *branch* dedicada e todos os membros devem registrar sua participação.

---

## 1. Estrutura de Branches

- A branch `main` é a branch principal.
- Cada grupo deve criar uma branch com o nome à critério.

## 2. Registro de Participação

Crie ou edite o arquivo **`turma.md`** na raiz do repositório. Cada membro deve:

1. **Assinar seu nome** na lista.
2. **Escrever uma breve mensagem** ao lado, descrevendo o que contribuiu ou um comentário relevante.

Exemplo de entrada em `turma.md`:

```markdown
1. Ana – Gostei muito da prática!
2. Bernardo – Achei chato :(
```

> **Importante:** Nunca altere a lista de outro grupo.

## 3. Fluxo de Trabalho Git

### 3.1. Configuração inicial
```bash
# Clone o repositório (se ainda não o fez)
git clone <url-do-repositório>
cd nivelamento-git
```

### 3.2. Trocar para a branch do seu grupo
```bash
# Substitua "grupo-X" pelo número do seu grupo
git checkout -b grupo-X
```

### 3.3. Desenvolvimento simultâneo (sem pull prévio)
> **Objetivo:** Permitir que vários membros façam *commits* ao mesmo tempo.

- **Faça suas alterações** nos arquivos que precisar.
- **Adicione** os arquivos modificados:
  ```bash
  git add <arquivo>
  ```
- **Commit** suas mudanças com uma mensagem clara:
  ```bash
  git commit -m "[Grupo X] Mensagem descritiva da alteração"
  ```
- **Push** direto para a branch do grupo (sem `git pull` antes):
  ```bash
  git push origin grupo-X
  ```

### 3.4. Resolvendo conflitos

Se dois ou mais membros alterarem a mesma parte do mesmo arquivo, o *push* pode falhar com um erro de **conflict**. Nessa situação:

1. **Faça pull** para obter as alterações dos colegas:
   ```bash
   git pull --rebase origin grupo-X
   ```
2. O Git abrirá o conflito nos arquivos afetados. Edite-os manualmente, removendo as marcas `<<<<<<<`, `=======` e `>>>>>>>` e decida qual conteúdo deve permanecer.
3. **Adicione** os arquivos corrigidos:
   ```bash
   git add <arquivo>
   ```
4. **Continue o rebase** (ou finalize o merge):
   ```bash
   git rebase --continue   # se usou --rebase
   # ou
   git commit --amend      # se for um merge simples
   ```
5. **Push** novamente:
   ```bash
   git push origin grupo-X
   ```

### 3.5. Integração à branch principal

Quando o trabalho do grupo estiver concluído e sem conflitos pendentes, crie um *pull request* da branch do seu grupo para a branch principal e aguarde a revisão.

---

## 4. Boas práticas
- **Commit frequentemente** e com mensagens descritivas.
- **Teste localmente** antes de fazer push.
- **Evite** editar arquivos que já foram modificados por outro membro da mesma branch simultaneamente.
- **Comunique** ao time através do `turma.md` ou de mensagens no PR.

## 5. Perguntas Frequentes
| Pergunta | Resposta |
|---|---|
| Posso fazer `git pull` antes de `git push`? | Para essa prática, não é recomendado; aguarde conflitos e siga o passo 3.4 se o push falhar. |
| O que fazer se houver conflitos repetidos? | Combine esforços com seu grupo via chat ou reuniões rápidas para decidir quem mantém qual parte do código. |
| Como registrar quem fez o que? | Utilize o `turma.md` conforme a seção 2. |

---

**Bom trabalho e colaboração!**
