# 🔐 SOLUÇÃO - Problema de Autenticação GitHub

## ❌ Problema Identificado

Você está tentando fazer push com o usuário **ElisMeli**, mas o repositório pertence a **Elisf2024**.

```
remote: Permission to Elisf2024/IranLigeiro.git denied to ElisMeli.
```

---

## ✅ SOLUÇÕES

### Opção 1: Limpar Credenciais do Windows (MAIS FÁCIL)

1. **Abrir Gerenciador de Credenciais do Windows**:
   - Pressione `Windows + R`
   - Digite: `control /name Microsoft.CredentialManager`
   - Pressione Enter

2. **Remover credenciais do GitHub**:
   - Clique em "Credenciais do Windows"
   - Procure por itens com "github" ou "git"
   - Clique em cada um e selecione "Remover"

3. **Tentar push novamente**:
   ```bash
   git push -u origin main
   ```
   
4. **Fazer login com Elisf2024**:
   - O Windows pedirá login
   - Use as credenciais da conta **Elisf2024**

---

### Opção 2: Usar Personal Access Token

1. **Criar Token no GitHub**:
   - Acesse: https://github.com/settings/tokens
   - Clique em "Generate new token (classic)"
   - Nome: "IranLigeiro Site"
   - Marque apenas: `repo` (acesso completo)
   - Clique em "Generate token"
   - **COPIE O TOKEN** (não conseguirá ver depois!)

2. **Fazer push com token**:
   ```bash
   git push https://TOKEN@github.com/Elisf2024/IranLigeiro.git main
   ```
   Substitua `TOKEN` pelo token copiado.

3. **Ou salvar o token no remote**:
   ```bash
   git remote remove origin
   git remote add origin https://TOKEN@github.com/Elisf2024/IranLigeiro.git
   git push -u origin main
   ```

---

### Opção 3: Usar GitHub CLI (RECOMENDADO)

1. **Instalar GitHub CLI** (se não tiver):
   - Baixe em: https://cli.github.com/
   
2. **Fazer login**:
   ```bash
   gh auth login
   ```
   - Escolha: GitHub.com
   - Escolha: HTTPS
   - Escolha: Login with a web browser
   - Siga as instruções

3. **Fazer push**:
   ```bash
   git push -u origin main
   ```

---

### Opção 4: Usar SSH (Mais Seguro)

1. **Gerar chave SSH**:
   ```bash
   ssh-keygen -t ed25519 -C "seu-email@example.com"
   ```
   Pressione Enter para aceitar local padrão.

2. **Copiar chave pública**:
   ```bash
   cat ~/.ssh/id_ed25519.pub
   ```

3. **Adicionar no GitHub**:
   - Acesse: https://github.com/settings/keys
   - Clique em "New SSH key"
   - Cole a chave copiada
   - Clique em "Add SSH key"

4. **Mudar remote para SSH**:
   ```bash
   git remote remove origin
   git remote add origin git@github.com:Elisf2024/IranLigeiro.git
   git push -u origin main
   ```

---

## 🎯 QUAL OPÇÃO ESCOLHER?

### Mais Fácil para Iniciantes:
- **Opção 1** - Limpar credenciais do Windows

### Mais Rápido:
- **Opção 2** - Personal Access Token

### Mais Profissional:
- **Opção 3** - GitHub CLI

### Mais Seguro:
- **Opção 4** - SSH

---

## ⚠️ VERIFICAÇÕES IMPORTANTES

Antes de fazer push, confirme:

1. **Repositório existe no GitHub?**
   - Acesse: https://github.com/Elisf2024/IranLigeiro
   - Se não existir, crie primeiro!

2. **Você está logado na conta certa?**
   - Verifique se está logado como **Elisf2024** no GitHub

3. **O repositório é público?**
   - Para usar GitHub Pages grátis, precisa ser público

---

## 🔄 COMANDOS PASSO A PASSO (Após corrigir autenticação)

```bash
# 1. Verificar remote
git remote -v

# 2. Se estiver correto, fazer push
git push -u origin main

# 3. Se der erro, remover e adicionar novamente
git remote remove origin
git remote add origin https://github.com/Elisf2024/IranLigeiro.git
git push -u origin main
```

---

## 📞 AINDA COM PROBLEMAS?

Se continuar dando erro:

1. Verifique se o repositório **IranLigeiro** foi criado no GitHub
2. Verifique se você tem permissão de escrita no repositório
3. Tente criar o repositório novamente: https://github.com/new

---

**Depois de resolver a autenticação, o push funcionará normalmente!** 🚀
