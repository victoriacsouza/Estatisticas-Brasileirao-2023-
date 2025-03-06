# Análise de Dados do Campeonato Brasileiro

Este repositório contém dois códigos desenvolvidos no Google Colab como parte do aprendizado em Python e Análise de Dados. Ambos os scripts utilizam a biblioteca Pandas para processar dados do Campeonato Brasileiro, extraídos do site [Football Data](https://www.football-data.co.uk/).

## Fonte dos Dados

Os dados foram obtidos do seguinte link: [BRA.xlsx](https://www.football-data.co.uk/new/BRA.xlsx), que contém informações sobre partidas do Campeonato Brasileiro, incluindo temporada, times mandantes e visitantes, e resultados das partidas.

## Código 1 - Estatísticas de Vitórias, Derrotas e Empates

Este script carrega os dados do arquivo Excel e filtra apenas os jogos da temporada 2023. Em seguida, processa os resultados das partidas para calcular:

- Número de vitórias por time
- Número de derrotas por time
- Número de empates por time

Os times são classificados de acordo com o número de vitórias, e os resultados são exibidos em formato tabular.

### Exemplo de saída:
```
| Ranking | Time         | Vitórias | Empates | Derrotas |
|---------|-------------|----------|---------|----------|
|    1    | Grêmio      |    21    |    5    |    12    |
|    2    | Palmeiras   |    20    |    10   |    8     |
|    3    | Flamengo    |    19    |    9    |    10    |
```

## Código 2 - Estatísticas com Pontuação

Este script segue a mesma lógica do primeiro, mas adiciona o cálculo da pontuação baseada no sistema tradicional:

- Vitória: 3 pontos
- Empate: 1 ponto
- Derrota: 0 pontos

Os times são classificados de acordo com a pontuação total, e os resultados são exibidos de forma tabular.

### Exemplo de saída:
```
| Ranking | Time         | Vitórias | Empates | Derrotas | Pontos |
|---------|-------------|----------|---------|----------|--------|
|    1    | Palmeiras   |    20    |    10   |    8     |   70   |
|    2    | Grêmio      |    21    |    5    |    12    |   68   |
|    3    | Flamengo    |    19    |    9    |    10    |   66   |
```

## Detalhamento do Código

O código está comentado em cada etapa para ajudar na compreensão do que está sendo feito. Isso facilita o entendimento e permite que você se familiarize com o funcionamento do código à medida que explora as partes do script.

### Montando o Google Drive

O código começa montando o Google Drive para acessar o arquivo Excel contendo os dados dos jogos.

### Carregando os Dados

O arquivo Excel é carregado usando `pd.read_excel()`. O DataFrame resultante é filtrado para manter apenas as colunas `Season`, `Home`, `Away` e `Res`.

### Filtragem para a Temporada de 2023

O DataFrame é filtrado para pegar apenas os jogos da temporada de 2023.

### Cálculo das Estatísticas

Para cada jogo da temporada de 2023, o código calcula as vitórias, derrotas e empates para os times de casa (`Home`) e visitante (`Away`), usando o valor da coluna `Res` que indica o resultado do jogo.

No segundo código, além das estatísticas de vitórias, derrotas e empates, também é calculada a pontuação de cada time com base no sistema tradicional de pontuação.

### Organização dos Dados

As estatísticas calculadas são armazenadas em um dicionário e depois convertidas para um novo DataFrame. A tabela é ordenada pela coluna `Vitórias` no primeiro código e pela coluna `Pontos` no segundo código. Um ranking é gerado automaticamente.

### Exibição da Tabela

A tabela final é exibida no formato de tabela Markdown usando a biblioteca `tabulate`, com as colunas `Ranking`, `Time`, `Vitórias`, `Empates`, `Derrotas` e, no segundo código, `Pontos`.

## Requisitos

Para executar os códigos, é necessário ter as seguintes bibliotecas instaladas:

- pandas
- tabulate
- google.colab (para acesso ao Google Drive)

No Google Colab, o arquivo deve estar armazenado no Google Drive do usuário, e o caminho de acesso ao arquivo deve ser ajustado conforme a estrutura de diretórios.

## Como Executar

1. Faça upload do arquivo `BRA.xlsx` para o Google Drive em uma pasta específica.
2. Monte o Google Drive no Google Colab.
3. Ajuste o caminho do arquivo conforme a localização no seu Drive.
4. Execute o código no Colab para visualizar os resultados.

## Resultado

Os resultados das análises são exibidos em formato tabular, ordenados pelo critério de classificação (Vitórias no primeiro código e Pontos no segundo).

## Autor

Este projeto foi desenvolvido como parte do aprendizado em Python e Análise de Dados.

---

