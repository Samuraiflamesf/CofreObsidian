---
{"title":"Data Discovery e Analytics","created":"2024-06-20","dg-publish":true,"tags":["pessoal/estudos","pessoal/puc","pessoal/web"],"permalink":"/1.Minha Vida/Data Discovery e Analytics/","dgPassFrontmatter":true}
---

| [Voltar](index) |
### KPI
KPI é indicador, sua criação é junção de Objetivos com as Métricas.
    O indicador e uma medica de ordem quantitativa ou qualitativa.
    Indicador aponta, mas não resolve os problemas.
**Finalidade**
    Começar com poucos indicadores, começar a fazer segregações em cada um. Ir inovando e modificando de acordo com demanada.
Quais objetivos tem que atingir?
    1. Pré diagnóstico
    2. Objetivo da mensuração
    3. Estabelecimentos do indicador
    4. Validação Preliminar
    5. Definição de responsáveis
    6. Construção de fórmulas
    7. Estabelecimento de metas
    8. Geração do sistema de coleta de dados
    9. Validação Final
    10. Mensurar o desempenho
Exemplo:
    Objetivo
        Usar os dados do NPS para aumentar o boca a boca do curso
    Métricas:
        Taxa de resposta do NPS
        Notas do NPS
    KPIs:
    70% de respostas do NPS
    100% dos detratores abordados
Para ter bons resultados é preciso ter objetivos estratégicos bem definidos...
...e ter dados organizados e disponíveis.

### SSD
São sistemas que daram apoio a solucionar um problema gerencial.
Modelo estático:
    Estabelecer relacionamentos
    Ex.: vender determinado produto a partir de um idade, renda ou outro
    dado do cosumidor.
Modelos dc previsão:
    Plataforma será alimentada com dados históricos
    Ex.: prever vendas e até mesmo o que a concorrência pode fazer no futuro.
Modelos de otimização:
    Ajuda a determinar quando alocar recursos para variáveis específicas
    Ex.: Definir quando um estoque deverá ser reposto para evitar     indisponibilidade de um item.
Modelos de análise de sensibilidade:
    Vão responder perguntas do tipo "o que se" para determinar as consequências ao alterar alguma decisão.
    Ex.: "0 que pode acontecer se eu elevar o preço de produto X em 5%?"
### OLAP
É utilização de ferramentas de análises de dados e Bi como armazenamento de dados, para ajudar na solução de problemas. 
### Arquitetura de um Projeto
![Pasted image 20240626132137.png](/img/user/0.Settings/img/Pasted%20image%2020240626132137.png)
A consolidação de todos os dados em um único repositório forma um Data Warehouse. Usando OLAP (Processamento Analítico Online), é possível acessar todo o conjunto de dados, mas selecionando apenas os dados específicos necessários para análise. O processo típico envolve a extração, transformação e carregamento (ETL) de dados do Data Warehouse para criar um Data Marts, que é um subconjunto de dados otimizado para análises específicas. Esses dados então passam por OLAP e são finalmente disponibilizados ao usuário final por meio de um cliente.
#### Ciclo de vida de Projeto de Dados
![Pasted image 20240628132646.png](/img/user/0.Settings/img/Pasted%20image%2020240628132646.png)


## Dicionario
KPI = Indicadores
NPS = Net Promoter Score é uma metrica de satisfação
    ![Pasted image 20240626124837.png](/img/user/0.Settings/img/Pasted%20image%2020240626124837.png)
SSD = Sistema de suporte a decisao
Queries = consultas
OLAP é projeto e construção de aplicações, Processamento analitico online
Data Mining ou KDD = minerar dados, ou seja, Buscar dados
Big Data = Conjuntos de dados gigantescos
DRILL/ROLL = Movimento de filtros, tem 4 tipos:
- Down-Descer um nivel
- Up-Sobre um nivel
- Across-Pula niveis, ou seja vai de 1 para 4
- Throught- Troca de oticas, Troca de dimensões, navegar entre hieraquias
PIVOT = É girar o cubo(dimensões)
## Conclusão
