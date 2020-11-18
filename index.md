# Descrição do projeto
<p align="center"><img src="./img/pexels-lukas-669610.jpg" alt="Unsupervised" width="600"/></p>

<p>Este projeto tem como objetivo analisar os dados de pesquisa relacionada às experiências dos alunos durante a disciplina de Projeto Integrador. Nesse contexto, foram consultados alunos do 2º ao 6º termo que se dispuseram voluntariamente a responder o formulário que contém 13 perguntas em torno do tema Metodologia de Gestão. Diante disso, os dados coletados passarão por todas as etapas de pré-processamento, mineração e discussão dos resultados a fim de identificar as principais dificuldades dos alunos durante o projeto. Por fim, os dados correlacionados nesse projeto auxiliará os alunos José Pedro e Iam Caio a embasar o estudo sobre a viabilidade de implementação de uma nova metodologia ágil de gestão de projetos.
</p>

# Características da pesquisa

<p>
Para dar início a coleta de dados foi elaborada uma pesquisa por meio da plataforma Google Forms. Esse formulário teve como público alvo alunos da disciplina de Projeto Integrador do 2º ao 6º termo, do qual obteve-se a resposta de 59 estudantes. A pesquisa em questão foi disponibilizada entre os dias 06/09/2020 à 15/09/2020 com foco em entender o nível de afinidade com a metodologia Scrum, trabalhada na disciplina, e as dificuldades que podem ser sanadas com o uso de outra metodologia de gestão de projetos de software para aumentar e melhorar a produtividade da equipe. Nesse contexto, foram exploradas cinco áreas de interesse para entender o ambiente de estudo, sendo:

<ul>
  <li>Método</li>
  <li>Técnicas</li>
  <li>Conceitos</li>
  <li>Princípios</li>
  <li>Experiências</li>
</ul>

Nesse contexto, todos os pilares acima foram relacionados pelos alunos diante a Metodologia Scrum já desenvolvida na disciplina. Sendo assim, após as análises feitas, podemos identificar os pontos positivos e negativos apresentados pelos alunos e propor ou não a introdução de uma nova metodologia de gestão de projetos de software que amenize as dificuldades.
</p>
<p>
Foi utilizada a escala Likert adaptada para medir a importância dos temas apresentados com a remoção da medida “Não Concordo e Nem Discordo” evitando a neutralidade das respostas. O conteúdo abordado visa também explorar as habilidades técnicas dos alunos, competências e habilidades pessoais necessárias para o trabalho em grupo e experiências com liderança em métodos ágeis.
</p>
<p>
No link abaixo, observa-se as perguntas e suas respectivas alternativas utilizadas no formulário de coleta de dados sobre a experiência dos alunos na utilização da metodologia Scrum, onde as opções em algumas perguntas são Discordo Totalmente (DT); Discordo Parcialmente (DP); Concordo Parcialmente (CP); Concordo Totalmente (CT).
</p>
<p>
O formulário juntamente com as perguntas pode ser acessado em: https://forms.gle/Ed3s2KDMzNzYfcKS9 
</p>

# Software utilizado

<p>
Para a análise dos dados coletados foi necessário um software que buscasse fazer todo o ciclo do Data Mining para que pudéssemos determinar e cruzar os dados para identificar padrões e possíveis pontos de melhoria metodológica no projeto integrador. Com base nisso, foi escolhido o Orange por ser Open-Source, conter uma ótima documentação e uma interface user-friendly.
</p>
<br/><br/>
<p align="center"><img src="./img/logo.png" alt="Orange" width="150"/></p>
<br/><br/>
Com o uso do Orange foi possível criar um fluxo de tratamento e extração de informação para encontrar padrões. Como exemplo, podemos detectar probabilidades de ocorrerem eventos por base de um histórico utilizando algoritmos disponíveis na plataforma. Nesse contexto, podemos encontrar algoritmos de Machine Learning supervisionados, não-supervisionados e redes neurais para utilização.
<br/><br/>
<p align="center"><img src="./img/unsupervised.png" alt="Unsupervised" width="200"/>
<img src="./img/model.png" alt="Model" width="200"/></p>
<br/><br/>
Como visto acima o Orange contém muitas opções de algoritmos para serem utilizados mas também temos vários meios de validar os resultados e métodos utilizados para buscar uma melhor acurácia do modelo.
<br/><br/>
<p align="center"><img src="./img/evaluate.png" alt="Evaluate" width="200"/></p>
<br/><br/>
Já em relação a visualização podemos ter uma interface simples e intuitiva para extrair informações relevantes e também visualizar dados e previsões feitas pelos algoritmos utilizando diversos modelos de gráficos.
<br/><br/>
<p align="center"><img src="./img/visualize.png" alt="Visualize" width="200"/></p>
<br/>

# Materiais e métodos

<p>
As etapas de manipulação dos dados feitas nessa pesquisa foram seguindo o processo de Knowledge Discovery in Databases (KDD) composto por seis etapas, sendo elas: entendimento do domínio; agrupamento de dados; pré-processamento; transformação; Data Mining; pós-processamento.
</p>

## Pré-processamento
<p>De início foi extraído o arquivo em formato .csv do formulário contendo todas as 59 respostas dos alunos. Após este passo foi identificado que havia 3 campos faltantes na coluna “FrontEnd” e que deveriam ser preenchidos. Nesse contexto foi realizado no software Orange o seguinte procedimento:
</p>

### a) Input de dados por meio da Árvore de decisão
<br/><br/>
<p align="center"><img src="./img/PrevFrontEnf.png" alt="Evaluate" width="500"/></p>
<br/><br/>

<p>
Como exposto acima, a Árvore de Decisão identificou por meio do cálculo do ganho de informação as classes que mais afetavam os valores contidos na variável Front-end. Nesse contexto, o algoritmo traçou a melhor probabilidade do preenchimento dos campos ausentes e nos retornou o seguinte resultado:
</p>
<br/><br/>
<p align="center"><img src="./img/ResultadoTree.PNG" alt="Evaluate" width="500"/></p>
<br/><br/>
<p>
Com isso, os 3 campos ausentes foram preenchidos com o valor “Intermediário” na classe Front-end.
</p>

### b) Renomeação de atributos para facilitar análises
<p>Seguindo o pré-processamento, foram simplificadas as respostas nas perguntas 04, 06 e 08, como exemplo:

<br/><br/>
<p align="center"><img src="./img/Perg6.PNG" alt="Evaluate" width="500"/></p>
<br/><br/>

Sabendo-se disso, foi utilizado o software Excel para renomear as respostas sendo  abreviadas para DT, DP, CP e CT.</p>

### c) Discretização de classes para facilitar análises
<p>Em relação a discretização, foi encontrado dificuldades em analisar as respostas nas perguntas 07 e 09 por conter múltiplas respostas em um único campo, como exemplo:

<br/><br/>
<p align="center"><img src="./img/MultiplasRespostas.PNG" alt="Evaluate" width="500"/></p>
<br/><br/>

Como a imagem acima, foram criadas as respectivas classes referenciando cada resposta, sendo feita posteriormente a binarização 0 ou 1 (sim ou não) de acordo com a resposta de cada aluno. Este processo irá facilitar a correlação de dados posteriormente. </p>

## Mineração

<p>
Visando entender as dificuldades dos alunos acerca dos Princípios e Práticas foram elaboradas perguntas norteadoras que buscam relacionar e compreender os métodos ágeis e o comportamento gerado com o uso desses métodos. As perguntas elaboradas estão apresentadas na tabela abaixo:
</p>

<table>
  <tr>
    <th>Número</th>
    <th>Pergunta</th>  
  </tr>
  <tr>
    <td style="text-align: center">1</td>
    <td>De acordo com os princípios de Transparência, Inspeção e Adaptação, qual deles mais influência para se ter uma equipe com desempenho bom (3)?</td>
  </tr>
  <tr>
    <td style="text-align: center">2</td>
    <td>Qual é a importância de se realizar cerimônias para se ter uma equipe com desempenho bom (3)?</td>
  </tr>
  <tr>
    <td style="text-align: center">3</td>
    <td>Qual a relação de se ter o conhecimento de BackEnd e FrontEnd diante uma equipe de desempenho bom (3)?</td>
  </tr>
</table>

<p>Foram utilizadas na pergunta de número 1 exibida na tabela acima as técnicas de Silhouettes Graph (ROUSSEEUW, 1987) para verificar a distância entre atributos e a qual cluster o mesmo pertence utilizando a escala de 0 a 1, sendo que quanto mais próximo de 1, mais ao centro o atributo se encontra do cluster; FreeViz (DEMŠAR; LEBAN; ZUPAN, 2007) sendo uma técnica que utiliza o algoritmo de otimização hill-climbing (CHALUP; MAIRE, 1999) para buscar um equilíbrio entre os vetores (atributos) de forma visual para destacar os vetores que são de extrema relevância; Logistic Regression (JR; LEMESHOW; STURDIVANT, 2013) visando a classificação do conjunto de dados para extrair os pesos encontrados por meio dele e Association Rules (AGRAWAL et al., 1994) com a finalidade de destacar as principais regras de associação baseado em uma confiança de 90% e suporte de 10%.
</p>
<p>
Na pergunta de número 2 também foram utilizadas as técnicas de  Silhouettes Graph (ROUSSEEUW, 1987); FreeViz (DEMŠAR; LEBAN; ZUPAN, 2007) e Logistic Regression (JR; LEMESHOW; STURDIVANT, 2013). Além disso, para esta análise foi adicionado o Support Vector Machine (SVM) (HEARST et al., 1998) utilizado na criação de um modelo de classificação.
</p>
<p>
Na pergunta de número 3 também foram utilizadas as técnicas de Association Rules (AGRAWAL et al., 1994) e Support Vector Machine (SVM) (HEARST et al., 1998). Adicionalmente, para compor esta análise foi aplicado o classificador Decision Tree, precursor do algoritmo Random Tree (BREIMAN, 2001), criando uma árvore com objetivo de determinar em qual classe aqueles atributos se assemelham e Scatter Plot sklearn (PEDREGOSA et al., 2011) gerando um gráfico de dispersão de dois eixos.
</p>

## Validação

<p>
No processo de validação dos métodos de aprendizado de máquinas foi utilizado a técnica Cross-Validation (HASTIE; TIBSHIRANI; FRIEDMAN, 2009) sendo utilizado 10 folds para o processo de validação cruzada juntamente com a técnica Confusion Matrix (VISA et al., 2011) para verificar a porcentagem de falsos-negativos e falsos-positivos. Com o objetivo de avaliar os modelos testados, foi utilizado o algoritmo Dummy Classifier para validar a acurácia mínima de classificação, sendo encontrado na biblioteca sklearn (PEDREGOSA et al., 2011).
</p>

<p>Referente as validações das perguntas, tivemos as seguintes informações:</p>

<li>Pergunta 1:</li>
<p align="center"><img src="./img/Pergunta1Acuracia.PNG" alt="Pergunta 1" width="400"/></p>

<li>Pergunta 2:</li>
<p align="center"><img src="./img/Pergunta2Acuracia.PNG" alt="Pergunta 2" width="400"/></p>

<li>Pergunta 3:</li>
<p align="center"><img src="./img/Pergunta3Acuracia.PNG" alt="Pergunta 2" width="400"/></p>
<br/>

# Resultados e discussão

<p>
Ao analisar a experiência dos alunos diante o ambiente da disciplina de Projeto Integrador, nota-se a importância da coleta de dados para o estudo de viabilidade de introdução de uma nova metodologia de gestão de projetos de software. Diante o contexto, a opinião dos alunos referentes ao desempenho da sua última equipe de projeto foi o atributo norteador para embasar os resultados das análises apresentadas. Nesse sentido, 54,2% dos estudantes afirmam que classificariam o desempenho da equipe como bom (3) em uma escala de 1 à 3, conforme mostrado na Figura 2.
</p>

<p align="center"><img src="./img/Grafico de Barras Ultima Equipe.png" alt="Distribuição de frequência das respostas quanto ao desempenho da sua última equipe de projeto integrador, classificado de ruim (1) à bom (3)" width="400"/></p>
<br/>

<p>
Baseado nas perguntas localizadas na tabela 2, pode-se observar os resultados encontrados abaixo:
</p>

<li>Pergunta 1: De acordo com os princípios de Transparência, Inspeção e Adaptação, qual deles mais influência para se ter uma equipe com desempenho bom(3)?</li>

<p>
A correlação exposta na Figura 3 foi realizada através da utilização da técnica de análise de componentes principais. Nesse sentido, o resultado apresentado demonstra que os alunos que Concordam Totalmente que seu último projeto integrador possuía Transparência em relação às tarefas do time, tem uma maior possibilidade de pertencer a uma equipe boa (3). Esse princípio se destaca diante a Inspeção e Adaptação que também foram consideradas atributos para a esta análise. 
</p>

<p align="center"><img src="./img/Grafico FreeViz.png" alt="Gráfico de projeção espacial com ênfase no eixo do princípio de Transparência concordado totalmente segundo as respostas dos alunos" width="400"/></p>
<br/>

<p>
De acordo com Aubert e Kelsey (2003), pode-se notar que todos os funcionários que apresentam alto desempenho também apresentavam alta transparência no compartilhamento de afazeres e atualizações para todas as suas equipes.
</p>

<cite>“High performers who trusted had high levels of transparency. In Team 2,information was shared to a great extent. Many quotes support the fact that they ensured high levels of transparency within their work,enabling all members to know what each one was doing, communicating frequently,and providing access to work already done.” (AUBERT; KELSEY, 2003)</cite>

<p>
Ou seja, ainda segundo o autor, a transparência corrobora para uma frequente comunicação relacionada ao acesso à todos os trabalhos realizados pela equipe.
</p>

# Conclusão

