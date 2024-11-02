---
title: Obsidian + Quartz 4
dg-publish: true
tags:
  - pessoal/estudos
  - pessoal/web
---
[Voltar](1.LIFE/index)
### Criando um blog gratuito com github + obsidian
Descubra como criar um blog fácil de manter e totalmente gratuito usando GitHub e Obsidian. Seguindo uma abordagem JAMstack minimalista e eficiente, seu blog exibirá conteúdo estático (JavaScript, CSS, HTML), eliminando a necessidade de um servidor de banco de dados.

> Utilizaremos o [Quartz 4](https://quartz.jzhao.xyz/), _gostei do visual do Quartz 4_.
> **Lista interessante com diversos exemplos de sites free com [obsidian](https://github.com/oleeskild/obsidian-digital-garden/issues/55).**

O melhor de tudo é que você pode publicar postagens diretamente do Obsidian sem sair do editor. Acompanhe os passos abaixo:
Abrir VS Code, abrir o terminar:
```
git clone https://github.com/jackyzha0/quartz.git
cd quartz
```
Agora, use o NPM para instalar essas dependências:
```
npm i
npx quartz create
```
Após a inicialização, você precisará escolher entre três opções de inicialização para o conteúdo em seu diretório:
```
- Empty Quartz
- Copy an existing folder
- Symlink an existing folder
```
Selecione `Empty Quartz`(Diretório vazio) usando as teclas de seta e pressione `Enter`. Você deverá ver algo assim:
```
Choose how Quartz should resolve links in your content. You can change this later in `quartz.config.ts`.
- Treat links as absolute path
- Treat links as shortest path
- Treat links as relative paths
```
Por padrão, Obsidian usa o caminho mais curto sempre que possível, então, a menos que você saiba que deseja alterar esse comportamento mais tarde, use as teclas de seta para selecionar a segunda opção, `Treat links as the shortest path`e pressione `Enter`.  Você deverá ver algo assim:

```
You're all set! Not sure what to try next? Try:
- Customizing Quartz a bit more by editing `quartz.config.ts`
- Running `npx quartz build --serve` to preview your Quartz locally
- Hosting your Quartz online (see: https://quartz.jzhao.xyz/hosting)
```
### Configure um repositório GitHub
Crie um repositorio e em _Repository name:_ , digite `quartz`(ou o que você escolheu anteriormente). 

Para _inicializar este repositório com:_ Certifique-se de que _Adicionar um arquivo README_ **NÃO** esteja marcado. Clique em _Criar repositório_ no final.
Vá de volta para Terminal:
```
git remote -v
```
Você deverá ver algo como: 
```
origin  https://github.com/jackyzha0/quartz.git (fetch)
origin  https://github.com/jackyzha0/quartz.git (push)
upstream        https://github.com/jackyzha0/quartz.git (fetch)
upstream        https://github.com/jackyzha0/quartz.git (push)
```
Execute:
```
git remote rm origin
```
E agora execute o controle remoto de volta:
```
git remote add origin https://github.com/yourusername/quartz.git
```
E finalize com:
```
npx quartz sync --no-pull
```
Você deverá receber algum texto de volta com um lindo verde `Done!`no final. Em caso de algum problema, pode tentar realizar via SSH, caso ainda haja problemas, verifica este [artigo](https://quartz.jzhao.xyz/setting-up-your-GitHub-repository).
### Configurando Obsidian
Para iniciar a criação, abra o Obsidian. Quando solicitado a abrir um cofre, selecione `Abrir pasta como cofre`. Navegue até o seguinte local `quartz`.
- Copiei `.obsidian/hotkeys.json`do meu cofre principal para o meu novo cofre, para que todos os meus atalhos de teclado funcionem no novo também.
- Pode tambem copiar toda a pasta `.obsidian`.
- Instalei e configurei plug-ins no novo cofre.
### Criando Template de Nota
O Quartz precisa de certas [propriedades](https://notes.nicolevanderhoeven.com/obsidian-playbook/Obsidian+Plugins/Core+Plugins/Properties+in+Obsidian) no [YAML Frontmatter](https://notes.nicolevanderhoeven.com/obsidian-playbook/Using+Obsidian/03+Linking+and+organizing/YAML+Frontmatter) para funcionar. Você _poderia_ simplesmente digitá-los a cada vez, mas eu sugiro usar um modelo para isso. Você pode usar o [plug-in principal](https://notes.nicolevanderhoeven.com/obsidian-playbook/Obsidian+Plugins/Core+Plugins/Core+plugins) [Templates](https://notes.nicolevanderhoeven.com/obsidian-playbook/Obsidian+Plugins/Core+Plugins/Templates) ou o plug-in da comunidade [Templater](https://notes.nicolevanderhoeven.com/obsidian-playbook/Obsidian+Plugins/Community+Plugins/Templater+plugin) . Eu escolhi o Templater, então instale e habilite-o antes de continuar.

No Obsidian, crie uma nota `templates`chamada `note`(ou como você quiser que ela seja chamada). Nessa nota, copie isto:

```
---
title: "How to publish Obsidian notes with Quartz on GitHub Pages"
tags:
  - 
---
```
Vá para Configurações > Modelo. Em _Local da pasta de modelos_ , digite `templates`.
### Criando sincronização com Github
Para garantir que seu site esteja funcionando perfeitamente antes de publicá-lo, é essencial testá-lo em seu computador. Para isso, você precisará "construir" o site usando um servidor Quark, que converte Markdown em HTML, permitindo que você visualize o site em seu navegador.

No terminal, execute o seguinte comando:
```
npx quartz build --serve
```
Você deverá ver um bloco de texto que inclui esta linha:
```
Started a Quartz server listening at http://localhost:8080
```

Abra seu navegador e digite `http://localhost:8080`. Você deverá ver seu site renderizado em seu navegador:
![quartzo-local-build.png](https://publish-01.obsidian.md/access/186a0d1b800fa85e50d49cb464898e4c/assets/quartz-local-build.png)
A página mostrada pode parecer diferente se você alterou seu conteúdo, mas o importante é que você veja suas alterações refletidas em seu navegador. Agora que você verificou que seu site é renderizado corretamente localmente, é hora de sincronizar suas alterações com o GitHub.

Execute este comando:
```
quartz build --serve
npx quartz sync
```
Este comando envia suas alterações para seu repositório GitHub online.

## Hospede seu cofre online

Neste ponto, você pode visualizar um site (a versão HTML renderizada de suas notas do Markdown) localmente, mas quando você sincroniza essas alterações com o GitHub, elas ainda estão apenas no repositório. Nesta etapa, você configurará seu repositório para que esses arquivos Markdown sejam gerados e publicados online.

### Crie um `deploy.yml`arquivo

No seu terminal, execute:

```
touch .github/workflows/deploy.yml
```
Abra o arquivo que você acabou de criar no Explorer.

Certifique-se de que os arquivos ocultos estejam visíveis

> `.github` é um arquivo oculto, então se você não o vê, clique em exibir, em `itens ocultos` selecione para vê-lo.<br> 
> ![Pasted image 20240611141839.png](/img/user/0.Settings/img/Pasted%20image%2020240611141839.png)

O arquivo em branco deveria ter sido aberto em seu editor de texto padrão. Agora copie e cole isto nele:
```
name: Deploy Quartz site to GitHub Pages
 
on:
  push:
    branches:
      - v4
 
permissions:
  contents: read
  pages: write
  id-token: write
 
concurrency:
  group: "pages"
  cancel-in-progress: false
 
jobs:
  build:
    runs-on: ubuntu-22.04
    steps:
      - uses: actions/checkout@v3
        with:
          fetch-depth: 0 # Fetch all history for git info
      - uses: actions/setup-node@v3
        with:
          node-version: 18.14
      - name: Install Dependencies
        run: npm ci
      - name: Build Quartz
        run: npx quartz build
      - name: Upload artifact
        uses: actions/upload-pages-artifact@v2
        with:
          path: public
 
  deploy:
    needs: build
    environment:
      name: github-pages
      url: ${{ steps.deployment.outputs.page_url }}
    runs-on: ubuntu-latest
    steps:
      - name: Deploy to GitHub Pages
        id: deployment
        uses: actions/deploy-pages@v2
```

( _Observação: isso foi atualizado em 25/01/2024. Se você estiver lendo isso muito depois disso, obtenha a versão mais recente na [documentação do Quartz](https://quartz.jzhao.xyz/hosting#github-pages) ._ )
**Salve o arquivo.**

Por que você não consegue ver este arquivo no Obsidian?

### Crie uma ação GitHub

No GitHub, vá para Configurações > Páginas.

Em _Origem_ , selecione _Ações do GitHub_ .

Então, volte para o seu terminal e sincronize. Lembre-se, isso é:

```
npx quartz sync
```

### Eis o seu novo site!

Verifique se funcionou visitando `https://yourusername.github.io/my-notes`seu navegador.

Você deverá ver seu site exibido, exatamente como o viu quando o construiu localmente.

Espere... isso é realmente grátis?

Você pode parar por aqui se estiver satisfeito com o novo URL acima. Mas e se você já tiver um domínio novinho em folha e quiser que seu site seja hospedado lá?

### Referências
1. [How to publish your notes for free with Quartz](https://www.youtube.com/watch?v=6s6DT1yN4dw)
2. [How to publish Obsidian notes with Quartz on GitHub Pages](https://notes.nicolevanderhoeven.com/)
3.  [Obsidian documentation](https://help.obsidian.md/Home)
4.  [Gilbert Sanchez](https://links.gilbertsanchez.com/)
5.  [Quartz documentation](https://quartz.jzhao.xyz/)
6.  [GitHub documentation](https://docs.github.com/)
7.  [GitHub Pages documentation](https://docs.github.com/en/pages)
