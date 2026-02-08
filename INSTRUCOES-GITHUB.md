# 🚀 Instruções para Publicar no GitHub

## Passo a Passo para fazer Push para seu GitHub pessoal (Elisf2024)

### 1. Criar Repositório no GitHub

1. Acesse: https://github.com/new
2. Nome do repositório: `IranLigeiro` (ou o nome que preferir)
3. Descrição: `Site oficial Iran Ligeiro - Hybrid Training`
4. Mantenha como **Público** (para usar GitHub Pages gratuitamente)
5. **NÃO** marque "Add a README file" (já temos um)
6. Clique em **Create repository**

### 2. Conectar o Repositório Local ao GitHub

No terminal (dentro da pasta `IranLigeiro-GitHub`), execute:

```bash
git remote add origin https://github.com/Elisf2024/IranLigeiro.git
git branch -M main
git push -u origin main
```

**Nota**: Substitua `IranLigeiro` pelo nome que você escolheu no passo 1.

### 3. Ativar GitHub Pages

1. No seu repositório no GitHub, vá em **Settings**
2. No menu lateral, clique em **Pages**
3. Em **Source**, selecione:
   - Branch: `main`
   - Folder: `/ (root)`
4. Clique em **Save**

Aguarde alguns minutos e seu site estará disponível em:
```
https://Elisf2024.github.io/IranLigeiro/
```

### 4. (Opcional) Configurar Domínio Personalizado

Se você tiver um domínio próprio (ex: `iranligeiro.com`):

1. Na mesma página de GitHub Pages (Settings > Pages)
2. Em **Custom domain**, adicione seu domínio
3. Configure os DNS do seu domínio para apontar para o GitHub Pages

### 5. Autenticação no GitHub

Se for a primeira vez fazendo push, o GitHub pode solicitar autenticação:

**Opção 1 - Personal Access Token (Recomendado)**:
1. Vá em: https://github.com/settings/tokens
2. Clique em **Generate new token (classic)**
3. Dê um nome (ex: "IranLigeiro Site")
4. Marque apenas o escopo `repo`
5. Clique em **Generate token**
6. Copie o token gerado (não conseguirá ver novamente!)
7. Use como senha quando o Git solicitar

**Opção 2 - GitHub CLI**:
```bash
gh auth login
```

### 6. Fazer Atualizações no Futuro

Sempre que fizer alterações no site:

```bash
git add .
git commit -m "Descrição das alterações"
git push
```

---

## ✅ Status Atual

- ✅ Repositório Git inicializado
- ✅ Commit inicial criado
- ✅ Arquivos prontos para push
- ⏳ Aguardando conexão com GitHub

## 📁 Arquivos no Repositório

- `index.html` - Página principal do site
- `README.md` - Documentação do projeto
- `.gitignore` - Arquivos ignorados pelo Git

## 🎨 Próximos Passos (Opcionais)

1. Adicionar Google Analytics
2. Otimizar imagens para carregamento mais rápido
3. Adicionar meta tags para SEO
4. Configurar sitemap.xml
5. Adicionar favicon personalizado

---

**Seu site está pronto para ser publicado! 🎉**

Qualquer dúvida, consulte este arquivo novamente.
