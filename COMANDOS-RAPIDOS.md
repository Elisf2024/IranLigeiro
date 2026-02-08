# 🚀 COMANDOS RÁPIDOS - Execute um por vez

## 1️⃣ PRIMEIRO: Limpar Credenciais (ESCOLHA UMA OPÇÃO)

### OPÇÃO A - Pelo Windows (Mais Fácil):
1. Pressione `Windows + R`
2. Digite: `control /name Microsoft.CredentialManager`
3. Remova todas as credenciais do GitHub
4. Volte aqui e execute o comando abaixo

### OPÇÃO B - Pelo Terminal:
```powershell
git config --global --unset credential.helper
git credential-manager-core erase
```

---

## 2️⃣ DEPOIS: Verificar se o repositório existe no GitHub

Acesse no navegador: https://github.com/Elisf2024/IranLigeiro

**Se NÃO existir:**
1. Acesse: https://github.com/new
2. Nome: `IranLigeiro`
3. Tipo: Público
4. NÃO adicione README
5. Clique em "Create repository"

---

## 3️⃣ FINALMENTE: Fazer Push

```bash
git push -u origin main
```

Quando pedir login, use as credenciais de: **Elisf2024**

---

## ⚡ SOLUÇÃO ALTERNATIVA RÁPIDA

Se quiser usar token direto (sem salvar credenciais):

1. Gere um token aqui: https://github.com/settings/tokens/new
   - Nome: `IranLigeiro`
   - Marque: `repo`
   - Clique em: Generate token
   - **COPIE O TOKEN**

2. Execute (substituindo SEU_TOKEN):
```bash
git remote remove origin
git remote add origin https://SEU_TOKEN@github.com/Elisf2024/IranLigeiro.git
git push -u origin main
```

---

## ✅ VERIFICAR SE DEU CERTO

Acesse: https://github.com/Elisf2024/IranLigeiro

Você deve ver seus arquivos lá!

---

## 🌐 ATIVAR GITHUB PAGES

Depois do push funcionar:

1. No repositório, vá em: **Settings**
2. Menu lateral: **Pages**
3. Source: `main` / `(root)`
4. Clique em: **Save**

Aguarde 2-3 minutos e acesse:
```
https://Elisf2024.github.io/IranLigeiro/
```

---

**PRONTO! Qualquer dúvida, consulte SOLUCAO-AUTENTICACAO.md** 📚
