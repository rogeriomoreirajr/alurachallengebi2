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
Nesta semana o desafio foi trabalhar com os dados de restaurantes cadastrados no [Zomato](https://www.zomato.com/) para tentar entender o mercado de restaurantes na Índia. Algo interessante deste caso é que, ao trabalhar com um país em outro continente (e do qual, provavelmente, pouco conhecemos) a análise não se aproveita de um conhecimento prévio nosso. Por isso, o caminho foi seguir com atenção e extrair as informações necessárias para responder às perguntas.
    
## 🎲Base de dados
O cliente entregou uma base de dados com dois tipos de arquivos:
- *Dados dos restaurantes:* vários arquivos json com informações sobre os restaurantes, como:
    - Dados de identificação (nome, foto do restaurante, url no app, id do restaurante)
    - Avaliações (nota, classificação, cor da classificação)
    - Localização (cidade, endereço, país, além de latitude e longitude)
    - Tipos de Culinária
    - Preço médio para duas pessoas
- *Codigos dos países:* um dicionário traduzindo os códigos de países
    
Além disso, achei que seria interessante ter análises que levassem em conta a população das cidades, e consegui dados do [Censo Indiano de 2011](https://censusindia.gov.in/2011census/population_enumeration.html). Por fim, fiz uma [planilha no Google Sheets](https://docs.google.com/spreadsheets/d/1UpGWd_YvPswGy_ccdVhPoVSZQVHePp4hY3z2ZzALj1w/edit?usp=sharing) com a cotação em Dólar das diversas moedas presentes no banco de dados (ainda que, nesse exercício, trabalhei só com as rupias indianas). A vantagem de ter esses dados no Google Sheets é que lá consigo usar a função `GOOGLEFINANCE` e ter uma cotação relativamente atualizada, sem precisar corrigir valores manualmente.
    
## 📏Métricas analisadas
O pedido do cliente era para análisar essas métricas:
- Filtrar por cidade, restaurantes e se tem reserva
- Total de restaurantes na Índia
- Preço médio
- Média de avaliação
- Porcentagem de restaurantes que tem ou não delivery online
- Cidades que mais possuem restaurantes
- Culinárias que mais são exploradas na Índia
- Restaurantes por cidade e suas classificações
    
E, claro, ficaríamos livres para explorar outras métricas. Resolvi explorar isso também.
    
Acho que uma tentação de quem tem uma base de dados ampla (no caso aqui, mais de 8 mil restaurantes) é explorar as diversas facetas desses dados em vários visuais criativos. Acontece que acredito que a nossa principal motivação não deve ser o *potencial* (o que consigo fazer?) mas sim o *negócio* (quais os dados que vão ns ajudar a tomar decisões). Cruzando as avaliações com informações geográficas, por exemplo, é possível chegar a alguns resultados. Mas dados demográficos básicos, como a população, nos ajudam a ter uma dimensão dos mercados - ainda mais, como já disse, trabalhando com dados de outros países.
