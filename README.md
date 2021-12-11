# Mineração de dados do Github 
Temos como objetivo neste trabalho realizar a mineração de dados no repositório Zulip, para tentar compreender o que faz uma issue ser classificada como dificil.

<h2> Integrantes</h2>

     Alisson             email: alisson.v3@hotmail.com
     Juan                email: juanrangel@alunos.utfpr.edu.br
     Lucas               email: 

# Execução
Para o desenvolvimento do projeto foi utilizado a linguagem <a href="https://www.python.org/downloads/">Python</a>  , em conjunto com a <a href="https://jupyter.org/install">IDE Jupyter Notebook</a>.

## Execução dos Notebooks
Divimos todo o processo em duas partes: a mineração e análise de dados. Para as executá-las se faz necessário instalar requisitos através do seguintes comando:

```bash
pip install requirements.txt 
```
Logo após a instalação dos requisitos, é necessário abrir o arquivo 'mineracao.ipynb' com o Jupyter Notebook, e dentro do arquivo, conterá as instruções para o uso do token do Github. Após a execução será gerado um arquivo '.csv', contendo os dados minerados. <br>

Com tudo isso feito, podemos abrir o arquivo 'visualizacao.ipynb' com o Jupyter Notebook, o qual conterá as visualizações e resutados obtidos através dos testes estátisticos para os atributos da base dos dados minerados.

# Metodologia
Utilizamos o módulo'PyGithub' para mineração dos dados de Pull Requests fáceis e difíceis do repositório Zulip. Como há mais dados de Pull Requests fáceis do que dificeis, optamos por separar as fáceis em dois conjuntos de mesmo tamanho das dificeis, os quais foram chamados de treino e validação. <br>

A partir desses conjuntos utilizamos técnicas estatísticas para analisar para cada atributo utilizando o teste Mann Whitney (p-value), e o valor de Effect Size (d), além de plotar boxplots para uma melhor visualização dos dados. 

# Resultados Obtidos
Após a analise de cada um dos atributos, dois resultados em específico chamaram a nossa atenção, sendo eles o atributo Size Body, que representa quantidade de caracteres no corpo de um Pull Request, e a Qtde Label, a qual representa o número de labels atribuído ao Pull Request. Abaixo podemos observar o boxplot de ambos atributos.
<p align="center">
    <img src="img/sizeBody.png" />
</p>

<p align="center">
    <img src="img/qtdLabelpng.png" />
</p>

Ambos rejeitaram a hipótese nula, ou seja, são estatísticamente diferentes, tanto para os dados de treino, tanto para os dados de validação, e ambos apresentam um alto índice do valor de effect size, ou seja, esses atributos representam uma maior importância em relação aos outros dados.

# Conclusão
Como é possível observar nos resultados obtidos, as variáveis de maior significância nos nossos dados são associadas ao Pull Request, e não a uma issue, ou seja, podemos concluir que há uma relação entre a definição da dificuldade e um Pull Request, e não a uma issue, já que os atributos associados a ela não possuem grande significância aos nossos dados.
