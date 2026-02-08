# 🔄 GERENCIAR MÚLTIPLAS CONTAS GITHUB

## ✅ Sim, você pode voltar com a credencial profissional!

Existem várias formas de trabalhar com múltiplas contas GitHub no mesmo computador.

---

## 🎯 OPÇÃO 1: Configuração por Projeto (RECOMENDADO)

Você pode definir qual usuário usar em cada repositório:

### Para o projeto IranLigeiro (conta pessoal):
```bash
cd C:\Users\fernandes\IranLigeiro-GitHub
git config user.name "Elisf2024"
git config user.email "elisf2024@gmail.com"
```

### Para projetos profissionais (conta trabalho):
```bash
cd C:\Users\fernandes\MeliFIT-GitHub
git config user.name "ElisMeli"
git config user.email "seu-email-profissional@meli.com"
```

**Vantagem**: Cada projeto usa automaticamente a conta correta!

---

## 🎯 OPÇÃO 2: Usar SSH com Múltiplas Chaves (MAIS PROFISSIONAL)

Esta é a melhor solução para trabalhar com múltiplas contas:

### 1. Criar chaves SSH separadas:

**Para conta pessoal:**
```bash
ssh-keygen -t ed25519 -C "elisf2024@gmail.com" -f ~/.ssh/id_ed25519_personal
```

**Para conta profissional:**
```bash
ssh-keygen -t ed25519 -C "seu-email@meli.com" -f ~/.ssh/id_ed25519_work
```

### 2. Configurar SSH config:

Crie/edite o arquivo `~/.ssh/config`:

```
# Conta Pessoal (Elisf2024)
Host github-personal
    HostName github.com
    User git
    IdentityFile ~/.ssh/id_ed25519_personal

# Conta Profissional (ElisMeli)
Host github-work
    HostName github.com
    User git
    IdentityFile ~/.ssh/id_ed25519_work
```

### 3. Adicionar chaves no GitHub:

**Conta Pessoal (Elisf2024)**:
1. Copie a chave: `cat ~/.ssh/id_ed25519_personal.pub`
2. Adicione em: https://github.com/settings/keys (logado como Elisf2024)

**Conta Profissional (ElisMeli)**:
1. Copie a chave: `cat ~/.ssh/id_ed25519_work.pub`
2. Adicione em: https://github.com/settings/keys (logado como ElisMeli)

### 4. Usar em cada projeto:

**IranLigeiro (pessoal):**
```bash
cd C:\Users\fernandes\IranLigeiro-GitHub
git remote set-url origin git@github-personal:Elisf2024/IranLigeiro.git
```

**MeliFIT (profissional):**
```bash
cd C:\Users\fernandes\MeliFIT-GitHub
git remote set-url origin git@github-work:ElisMeli/MeliFIT.git
```

---

## 🎯 OPÇÃO 3: Gerenciador de Credenciais (Windows)

O Windows salva credenciais por domínio. Você pode:

### Manter ambas:
- O Windows vai perguntar qual usar quando necessário
- Ou você escolhe qual credencial usar por projeto

### Alternar manualmente:
```powershell
# Ver credenciais salvas
cmdkey /list | findstr git

# Remover credencial atual
cmdkey /delete:LegacyGeneric:target=git:https://github.com

# No próximo push, digite a credencial que quiser usar
```

---

## 🎯 OPÇÃO 4: Git Credential Manager (AUTOMÁTICO)

O Git Credential Manager pode gerenciar múltiplas contas automaticamente:

```bash
# Configurar para perguntar sempre qual conta usar
git config --global credential.useHttpPath true
```

Com isso, o Git vai associar a credencial ao caminho completo do repositório.

---

## 📋 FLUXO DE TRABALHO RECOMENDADO

### Para Projetos Pessoais (IranLigeiro):
```bash
cd IranLigeiro-GitHub
# Usa automaticamente Elisf2024 (se configurado por projeto)
git pull
git push
```

### Para Projetos Profissionais (MeliFIT):
```bash
cd MeliFIT-GitHub
# Usa automaticamente ElisMeli (se configurado por projeto)
git pull
git push
```

---

## ✅ RESUMO - O QUE FAZER AGORA

### 1. **Publicar IranLigeiro (agora)**:
- Remova a credencial ElisMeli
- Faça push com Elisf2024
- Configure o projeto para usar Elisf2024

### 2. **Configurar projetos separados**:
```bash
# IranLigeiro - pessoal
cd C:\Users\fernandes\IranLigeiro-GitHub
git config user.name "Elisf2024"
git config user.email "elisf2024@gmail.com"

# MeliFIT - profissional
cd C:\Users\fernandes\MeliFIT-GitHub
git config user.name "ElisMeli"
git config user.email "seu-email-meli@email.com"
```

### 3. **Voltar a usar ElisMeli quando precisar**:
- Basta entrar em um projeto configurado com ElisMeli
- O Git vai usar automaticamente as configurações daquele projeto

---

## 🔐 SEGURANÇA

### Usar Personal Access Tokens:
- Mais seguro que senhas
- Pode criar um token para cada projeto
- Revogue tokens que não usar mais

**Tokens separados**:
- `IranLigeiro-Token` → Para conta Elisf2024
- `MeliFIT-Token` → Para conta ElisMeli

---

## 💡 DICA PROFISSIONAL

**Melhor abordagem**:
1. Use **SSH** para trabalho profissional (mais seguro)
2. Use **HTTPS + Token** para projetos pessoais (mais simples)
3. Configure `user.name` e `user.email` em cada repositório

Assim você nunca vai confundir as contas!

---

## 🎯 RESPOSTA CURTA

**SIM!** Você pode:
1. Usar Elisf2024 agora para publicar IranLigeiro
2. Voltar a usar ElisMeli depois para MeliFIT
3. Alternar entre as duas sempre que quiser

Basta configurar cada repositório com o usuário correto (comandos acima).

---

**Não se preocupe! Suas credenciais profissionais não serão perdidas.** ✅
