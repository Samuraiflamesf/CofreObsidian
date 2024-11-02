---
title: Plugin Dataview Serialize
draft: false
dg-publish: true
tags: pessoal/estudos
---
| [Voltar](index) |
## Resumo
Plugin para fazer o "Dataview" virar markdown, afim de funcionar com [[1.Minha Vida/Obsidian_quartz4\|Obsidian_quartz4]] ou [Obsidian Publish](https://obsidian.md/publish), funciona com função `LIST` e `TABLE`.
### Uso
Este plugin automatiza a serialização das consultas Dataview personalizadas em suas anotações. Sempre que você salvar uma anotação (que ocorre no máximo a cada 3 segundos), as consultas serão serializadas. Observe que as consultas devem ser organizadas em uma estrutura específica para que o plugin as identifique adequadamente:As consultas precisam ser agrupadas em uma estrutura muito específica para que o plugin as reconheça:
```
<!-- QueryToSerialize: <query> -->
```
As tags envoltas por comentários HTML são compatíveis com Markdown e Obsidian. Elas permanecem ocultas na visualização normal, aparecendo apenas no modo de código fonte.
Além disso, os códigos dentro das tags de comentários HTML não são reconhecidos pela Obsidian. Portanto, ao utilizar uma tag em uma consulta, ela não será identificada como uma tag válida. **Exemplo de consulta:**
```
<!-- QueryToSerialize: LIST FROM #quotes WHERE public_note = true SORT file.name ASC -->
```
### Referências
2. Este plugin é um [projeto de código aberto](https://github.com/dsebastien/obsidian-dataview-serializer) , criado por [Sébastien Dubois](https://dsebastien.net/) .
1. [Documentação](https://developassion.gitbook.io/obsidian-dataview-serializer)
  