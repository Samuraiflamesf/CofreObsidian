---
{"title":"Aprendendo Git","created":"2024-09-28","dg-publish":true,"tags":["pessoal/estudos","pessoal/quaseumdev","git"],"permalink":"/1-minha-vida/aprendendo-git/","dgPassFrontmatter":true}
---

| [Voltar](index) | [[1.Minha Vida/Git Flow\|Git Flow]] | [[1.Minha Vida/PHP_Artisan\|PHP_Artisan]] |
### **Inicialização do Projeto:**
**Criar um novo repositório Git.**
```bash
git init
```
**Para adicionar todos arquivos e criar um commit**
```bash
git commit -am 'Feat: Enviando email, sobre contatos'
```
**Subindo para nuvem**
```bash
git push origin name_branch
```
****
### **Puxando um Projeto:**
**Clonando o repositorio:**
```bash
git clone https://github.com/usuario/repositorio.git
```
**Comece a editar os arquivos**:
```bash
cd repositorio
code .
```
**Sincronização Pré-Edições:**
```bash
git pull origin main
```
_Substitua "main" pelo nome da sua branch principal, se necessário._
**Criação de Branch:**
```bash
git checkout -b minha-branch
```
****
### Sobre Branch
**Para listar todas as branches locais**, utilize o comando:
```bash
git branch
```
**Para remover uma branch local**, use o seguinte comando:
```bash
git branch -d nome-da-branch
```
Para listar as branches remotas, você pode usar:
```bash
git branch -r
```
Para remover uma branch remota, utilize o comando:
```bash
git push origin --delete nome-da-branch
```
**Criação de uma Nova Branch:**
```bash
git checkout -b "nome"
```
**Comando para atualizar as branch do projeto:**
```bash
git fetch
```
**Selecionar branch e atualizar:**
```bash
git pull origin nome_da_branch
```
**Comando para atualizar as branch do projeto:**
```bash
git push origin feature/mailtrap-contact
```
#### Baixar versão mais recente da branch
Resolva os conflitos pendentes, conforme descrito anteriormente:
```bash
git status
```
Após resolver qualquer conflito ou problema pendente, **descarte as alterações locais** se você não precisar mantê-las:
```bash
git reset --hard
```
Certifique-se de estar na branch onde deseja baixar as atualizações:
```bash
git checkout feature/mailtrap-contact
```
Agora, faça o **pull** para baixar a versão mais recente da branch remota:
```bash
git pull origin feature/mailtrap-contact
```
***
### Setup inicial de projeto Laravel
**Clonando projeto**
```bash
git clone Samuraiflamesf/StudyCMS.git
```
**Copie o arquivo .env.example**
```bash
cp .env.example .env
```
**Instale as dependências e o framework**
```bash
composer install
```
**Crie uma nova chave para a aplicação**
```bash
php artisan key:generate
```
**Rodando migrates**
```bash
php artisan migrate
```
***

<div class="transclusion internal-embed is-loaded"><a class="markdown-embed-link" href="/3-caixa-de-entrada/git-tricks-bug-and-fix/" aria-label="Open link"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="svg-icon lucide-link"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"></path><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"></path></svg></a><div class="markdown-embed">




| [Voltar](index) | [[1.Minha Vida/Aprendendo Git\|Aprendendo Git]] |
**Erro "fatal: remote origin already exists":**
* Esse erro ocorre quando um controle remoto com o mesmo nome já existe.
* Para resolvê-lo, execute:
```bash
git remote rm origin
```
**fatal: not a git repository (or any of the parent directories): .git**
* Para resolvê-lo, execute:
```bash
git init
```
**fatal: The current branch feature/new-migrate-stability has no upstream branch.**
* Para resolvê-lo, execute:
```bash
git config --global --add --bool push.autoSetupRemote true
```

</div></div>

