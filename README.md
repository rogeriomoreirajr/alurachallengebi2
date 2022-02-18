# Alura Challenge BI

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
![1ª tela](https://github.com/rogeriomoreirajr/alurachallengebi2/blob/main/imagens/Screenshot_1.png?raw=true)
![1ª tela com ajuda](https://github.com/rogeriomoreirajr/alurachallengebi2/blob/main/imagens/Screenshot_4.png?raw=true)
![2ª tela](https://github.com/rogeriomoreirajr/alurachallengebi2/blob/main/imagens/Screenshot_2.png?raw=true)
![3ª tela](https://github.com/rogeriomoreirajr/alurachallengebi2/blob/main/imagens/Screenshot_3.png?raw=true)
