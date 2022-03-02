# Alura Challenge BI

- [Semana 1](#semana-1---alura-filmes)
- [Semana 2](#semana-2---alura-foods)

Desafio da Alura, em quatro semanas, para colocar em prática o que aprendemos sobre BI. O foco está em limpar e modelar os bancos de dados e também pensar nas visualizações que vão responder as necessidades do negócio.

## Ferramentas
O trabalho foi desenvolvido no Power BI, usando o M para otimizar a importação dos dados e o DAX para calcular as medidas.
Também usei outras ferramentas de design para criar os planos de fundo.

# 🎞Semana 1 - Alura Filmes
A partir do banco de dados de mil filmes tentar entender quais fatores podem influenciar na faturamento, e dar subsídio para decisões futuras.

## 🎲Base de dados
O Desafio nos entregou dois arquivos CSV:
- `Filmes.csv` com dados como faturamento, avaliação do público, elenco, classificação, gênero (muitas vezes mais de um, separados por vírgula), ano de lançamento e resumo.
- `Posters.csv`com os endereços para imagens dos pôsters

## 📏Métricas analisadas
- Média de faturamento por artista
- Faturamento por categoria e por gênero
- Notas dos filmes por artista

## 🛠 Desafios e aprendizados
- Filmes com muitos gêneros
    - Como um mesmo filme tinha mais de um gênero (tudo numa mesma coluna, numa string separada por vírgulas) precisei criar uma consulta dependente onde separei os gêneros para novas linhas, e depois relacionar os `ids` dos filmes com a tabela principal.
    - O problema é que essa cardinalidade `*:1` (n gêneros : 1 filme) não filtrava os `ids`. Para resolver isso, descobri que tinha que mudar a direção do filtro cruzado para **ambas.** Assim os filtros passaram a funcionar.
- Usar os indicadores como elemento de navegação
    - É claro que o objetivo desse Desafio é o aprendizado e exercício, e não, de fato, descobrir uma “fórmula” do sucesso. Para explicar isso no gráfico, usei um botão na primeira tela para trazer um texto explicando isso.

## 📊 Resultado
> _Clique na imagem para acessar o dashboard_
<div><a href = "https://app.powerbi.com/view?r=eyJrIjoiNDcwNmFiNjEtODgxNi00OGVhLTg4OGUtM2I5OGFmOTYyMzZlIiwidCI6IjFmZmFiMzhmLWU5MjAtNDFiZS05MjU1LTNhYmEzNjMwNmI4OCJ9&pageName=ReportSectiona03887976dcd9d368c09">
<img align="center" src="https://github.com/rogeriomoreirajr/alurachallengebi2/blob/main/imagens/Screenshot_1.png?raw=true">
<img align="center" src="https://github.com/rogeriomoreirajr/alurachallengebi2/blob/main/imagens/Screenshot_4.png?raw=true">
<img align="center" src="https://github.com/rogeriomoreirajr/alurachallengebi2/blob/main/imagens/Screenshot_2.png?raw=true">
<img align="center" src="https://github.com/rogeriomoreirajr/alurachallengebi2/blob/main/imagens/Screenshot_3.png?raw=true">
    </div>

# 🥗Semana 2 - Alura Foods
# Alura Challenge BI
Nesta semana o desafio foi trabalhar com os dados de restaurantes cadastrados no [Zomato](https://www.zomato.com/) para tentar entender o **mercado de restaurantes na Índia**. Algo interessante deste caso é que, ao trabalhar com um país em outro continente (e do qual, provavelmente, pouco conhecemos) a análise não se aproveita de um conhecimento prévio que se possa ter. Assim, sem o apoio do nosso pré-conhecimento (e preconceito) só nos resta se basear nas informações que os dados trazem.

# 🎲Base de dados
O Cliente entregou uma base de dados com dois tipos de arquivos:
- **Dados dos restaurantes***:* vários arquivos *json* com informações sobre os restaurantes, como:
    - Dados de identificação (nome, foto do restaurante, url no app, id do restaurante)
    - Avaliações (nota, classificação, cor da classificação)
    - Localização (cidade, endereço, país, além de latitude e longitude)
    - Tipos de Culinária
    - Preço médio para duas pessoas
- **Códigos dos países:** um dicionário traduzindo os códigos de países

Achei que também seria interessante ter análises que levassem em conta a população das cidades, e consegui esses dados no [**Censo Indiano de 2011**](https://censusindia.gov.in/2011census/population_enumeration.html).

Por fim, fiz uma [planilha no Google Sheets](https://docs.google.com/spreadsheets/d/1UpGWd_YvPswGy_ccdVhPoVSZQVHePp4hY3z2ZzALj1w/edit?usp=sharing) com a cotação em Dólar das diversas moedas presentes no banco de dados (ainda que, nesse exercício, o Cliente tenha pedido para trabalhar só com os restaurante da Índia). A vantagem de ter esses dados no Google Sheets é que a função `GOOGLEFINANCE` fornece uma cotação relativamente atualizada, sem que se precise corrigir valores de cotação manualmente.

## 📏Métricas analisadas
O Cliente pediu a análise dessas métricas:
- Filtrar por cidade, restaurantes e se tem reserva
- Total de restaurantes na Índia
- Preço médio
- Média de avaliação
- Porcentagem de restaurantes que tem ou não delivery online
- Cidades que mais possuem restaurantes
- Culinárias que mais são exploradas na Índia
- Restaurantes por cidade e suas classificações

E, claro, ficaríamos livres para avaliar outras métricas. Resolvi explorar isso também.

Acho que uma tentação de quem tem uma base de dados ampla (no caso aqui, mais de 8 mil restaurantes) é explorar as diversas facetas desses dados em vários visuais criativos. Entretanto, penso que nosso objetivo não deve ser *quanto podemos fazer,* mas sim *o que o negócio pede* (quais os dados que vão ajudar na tomada de decisões).

O dashboard não é medido pelo quanto é criativo, ou quantos visuais diferente e inovadores usou. Claro que isso pode gerar um “efeito wow” na primeira vez que o olhamos. Mas visualizações são ferramentas, e são medidas pela sua utilidade para o usuário (mesmo que só usem gráficos de barras e linhas, por exemplo).

É por isso que fui atrás dos dados demográficos antes de procurar fazer gráficos com o que já tinha. Cruzando as avaliações com o tipos de culinária dos restaurantes, por exemplo, é possível saber as preferências das populações de cada cidade. Mas ao conhecer a população conseguimos uma dimensão dos mercados - o quanto está saturado, e quais oportunidades escapam a uma primeira vista. E isso é ainda mais importante quando estamos trabalhando com dados de outros países.

## 🧹Tratamento e limpeza dos dados
Deixei os passos de tratamento no Power Query simples e claros, mas vale a pena destacar alguns pontos aqui:

- O processo de trabalhar com o Json é mais moroso do que um CSV, ou Excel - com uma série de “expansões” para que o dados fiquem no formato de tabela. Traduzi o nome das colunas para o português, filtrei as linhas duplicadas (havia várias!), tirei as colunas inúteis e usei uma Coluna de Exemplos para criar uma ordem para as avaliações (com “Excellent” no topo e “Not Rated” na base). Salvei isso na tabela `restaurantes`
- Além disso, criei uma consulta dependente dessa para lidar com os diferentes tipos de culinária. Isso porque, na base original, os diferentes tipos de cozinha são registrados num único campo, separado por vírgulas (como `Continental, American, Asian, North Indian`). Na nova consulta, `cozinhas`, eu mantive o `id` dos restaurantes e separei os estilos de cozinha em novas linhas. Depois relacionei essa consulta com a `restaurantes` pela `id`  dos restaurantes, numa relação *:1 bidirecional.
- No caso da cotação das moedas, como disse acima, fiz uma conexão com uma [planilha no Google Sheets](https://docs.google.com/spreadsheets/d/1UpGWd_YvPswGy_ccdVhPoVSZQVHePp4hY3z2ZzALj1w/edit?usp=sharing). Relacionei com `restaurantes` pela `id` do país.
- A planilha do Censo (que consegui no site do *Office of the Registrar General & Census Commissioner*) precisou de uma limpeza especial.
    - Em primeiro lugar, o Excel tinha um cabeçalho e rodapé, e várias colunas que não interessavam para a análise demográfica (como separar a população em Rural e Urbana).
    - Cinco cidades do **Zomato** não apareciam na lista do censo, por causa de grafias alternativas. Tive que fazer essa substituição na mão.
    - Aparentemente o **Zomato** coloca na coluna “City” tanto Distritos quanto Subdistritos. Por isso, não foi possível selecionar só os Distritos para fazer um merge entre as duas tabelas (isso seria mais fácil se eles seguissem o código indiano para as cidades). Além disso, 27 dos 43 nomes de cidades (como “Agra”) correspondem tanto a Distritos quanto Subdistritos. Assim, decidi escolher sempre o menor valor (ou seja, existindo os dois, retornar a população do subdistrito).

        > O motivo para seguir assim não é arbitrário. Nesses casos de dados ambíguos podemos cometer dois erros:
        >
        > 1. Considerar que uma cidade tem uma **população maior** do que a realidade
        > 2. Considerar que uma cidade tem uma **população menor** do que a realidade
        >
        > O erro 1 tem a desvantagem de nos impedir de ver oportunidades numa região (se um distrito tem 500 mil habitantes e eu uso o dado do subdistrito, com 100 mil, o mercado é cinco vezes maior do que estou considerando). Mas o erro 2 tem consequências piores: posso descobrir que os restaurantes concorrentes estão todos concentrados na área do subdistrito, e o mercado está mais saturado do que eu esperava.
        >
        > Embora, é claro, falo isso a nível de exercício. **Numa situação real, o caminho seria procurar uma base de dados que seja mais específica na notação geográfica para relacionar essas duas informações**.


## 📏 Métricas

Além de algumas medidas criadas para ordenar legendas e menus (como, por exemplo, colocar as cidades com mais população no topo, ou as culinárias com mais representantes), reuni as medidas numa tabela única. Destaco algumas:

`custoParaDois = AVERAGEX(restaurantes,restaurantes[custoParaDois]*RELATED(cotacao[paraDolar]))`
> usando o dado original de “custo para duas pessoas”, converti ele para dólar.

`nomeCulinaria = "Dados "&if(ISFILTERED(cozinhas[cozinhaEspecifica]),"de "&MAX(cozinhas[cozinhaEspecifica]), "gerais das culinárias")`
> Usei essa medida para que, quando nenhuma culinária estivesse selecionada, ele mostrasse o texto "Dados gerais das culinárias". Fiz algo parecido para a visualização das cidades.

`População por Restaurante = divide(divide(AVERAGE(censoSelecionados[populacao]),10^3), COUNTROWS(restaurantes))`
> Essa medida serviu para calcular a saturação do mercado. O que fiz foi dividir a população do local (multiplicada por mil) pela quantidade de restaurantes ali. É claro que o valor normalmente usado é o de “restaurantes a cada mil pessoas”, no sentido inverso, mas organizar o divisor e dividendo assim tem a vantagem de que **quanto maior o resultado, menos restaurantes há por pessoa** - e, por extensão, mais o mercado deve estar pronto para receber novos estabelecimentos.

Além disso, criei compartimentos para os valores `custoParaDoisDolar` e `avaliacaoAvaliacao`  para poder montar histogramas que permitissem visualizar a distribuição dos valores.

## 📊Visualizações
Tendo essas métricas em mãos, montei três dashboards, cada um respondendo uma pergunta:

----
- Já tenho uma ideia de qual vai ser o nosso tipo de cozinha. **Qual a melhor cidade** para abrir o restaurante?
<div><a href = "https://app.powerbi.com/view?r=eyJrIjoiZDAyYzY2YTMtOTRjOC00NzEwLWFkMDAtYTMwOWE1NzEzMDcwIiwidCI6ImJmOTE3MWEwLTFhNzItNGE0Mi1hNGEzLTEwNTllNDllMjQzMCJ9">
<img align="center" src="https://github.com/rogeriomoreirajr/alurachallengebi2/blob/main/Semana%202/imagens/Screenshot_2.png?raw=true"></a>
</div>

----
- Já tenho uma ideia de em que cidade vamos investir. **Qual o melhor tipo de cozinha** para o restaurante?
<div><a href = "https://app.powerbi.com/view?r=eyJrIjoiZDAyYzY2YTMtOTRjOC00NzEwLWFkMDAtYTMwOWE1NzEzMDcwIiwidCI6ImJmOTE3MWEwLTFhNzItNGE0Mi1hNGEzLTEwNTllNDllMjQzMCJ9">
<img align="center" src="https://github.com/rogeriomoreirajr/alurachallengebi2/blob/main/Semana%202/imagens/Screenshot_3.png?raw=true"></a>
</div>

----
- Quais são os **dados gerais** do mercado de restaurantes indiano?
<div><a href = "https://app.powerbi.com/view?r=eyJrIjoiZDAyYzY2YTMtOTRjOC00NzEwLWFkMDAtYTMwOWE1NzEzMDcwIiwidCI6ImJmOTE3MWEwLTFhNzItNGE0Mi1hNGEzLTEwNTllNDllMjQzMCJ9">
<img align="center" src="https://github.com/rogeriomoreirajr/alurachallengebi2/blob/main/Semana%202/imagens/Screenshot_4.png?raw=true"></a>
</div>

----

Nas duas primeiras telas decidi usar um gráfico de dispersão para relacionar a **disponibilidade do mercado** com a **média de notas** que os restaurantes tem. A lógica é que a melhor estratégia seria escolher um tipo de culinária que é **amado pelas pessoas** (ou seja, elas dão boas notas para os restaurantes que frequentam) e que tem **poucos restaurantes** deste tipo.
<div><a href = "https://app.powerbi.com/view?r=eyJrIjoiZDAyYzY2YTMtOTRjOC00NzEwLWFkMDAtYTMwOWE1NzEzMDcwIiwidCI6ImJmOTE3MWEwLTFhNzItNGE0Mi1hNGEzLTEwNTllNDllMjQzMCJ9">
<img align="center" src="https://github.com/rogeriomoreirajr/alurachallengebi2/blob/main/Semana%202/imagens/Screenshot_1.png?raw=true"></a>
</div>

----
É claro que o gráfico de dispersão não é tão popular, nem tão rápido de ser lido quanto um gráfico de barras ou linha. Para isso, fiz uma imagem de ajuda que explica os eixos.
<div><a href = "https://app.powerbi.com/view?r=eyJrIjoiZDAyYzY2YTMtOTRjOC00NzEwLWFkMDAtYTMwOWE1NzEzMDcwIiwidCI6ImJmOTE3MWEwLTFhNzItNGE0Mi1hNGEzLTEwNTllNDllMjQzMCJ9">
<img align="center" src="https://github.com/rogeriomoreirajr/alurachallengebi2/blob/main/Semana%202/imagens/Screenshot_5.png?raw=true"></a>
</div>

Uma linha mostrando a média em cada eixo ajuda e dividir os quadrantes. Além disso, tooltips personalizadas dão mais informações tanto sobre os restaurantes, as cidades e os gêneros culinários.

Por fim, a última tela dá um panorama geral sobre o mercado indiano, com os principais indicadores. 
