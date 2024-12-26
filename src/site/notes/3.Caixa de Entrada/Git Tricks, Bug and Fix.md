---
{"Title":"Git: Tricks, Bug and Fix","created":"2024-12-16","dg-publish":true,"tags":["pessoal/estudos","pessoal/quaseumdev","git"],"permalink":"/3-caixa-de-entrada/git-tricks-bug-and-fix/","dgPassFrontmatter":true}
---

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