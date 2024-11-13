# Projeto Final da Disciplina de Redes Neurais
*Programa de Mestrado em Computação Aplicada IFES*

# Proposta

O mercado de animação japonesa (anime) tem como objetivo primário servir como marketing para a alavancagem de venda de material original (quadrinhos, livros, jogos e artigos de colecionador), que representam a fonte massiva de renda deste setor. Assim, a decisão de investir na criação do anime se dá ao se avaliara receita do aumento das vendas de material original, subtraído do custo de produção da animação[5].

Uma forma já explorada pela indústria é a análise de redes, abordando o problema de decisão de fazer ou não uma animação como um problema de recomendação[1]. Outra forma de se abordar este caso é não sobre a decisão de investir na criação do anime mas, após ele ser feito, maximizar a exposição dele dentro do público que está mais propenso a gostar e consumir o material original[3, 4].

Diferente do convencional, esta proposta aborda o problema em uma ótica holística, fundamentando-se em na cadeia do processo de tomada de decisão. A base da proposta é a criação de um modelo que seja capaz de, dado um usuário e uma possível obra a ser animada, informar se o usuário gostará da obra animada ou não. Com este modelo, uma próxima etapa consiste em gerar a segmentação de público, que serve de auxílio ao processo de análise de cenário.

Ao final, os tomadores de decisão terão a sua disposição um sistema onde eles poderão criar os cenários e avaliar qual o possível impacto, de modo a verificar a sua viabilidade. O fluxo começa com o informe dos dados de uma possível produção de anime e a seleção do público que se deseja atingir. O modelo retorna a porcentagem de pessoas, em cada público, que gostará desta obra, dado que serve como proxy para a quantidade de pessoas com potencial de consumir o material original. Em resumo, dada uma possibilidade de animação, o tomador de decisão poderá saber a quantidade de leads quentes e, desta forma, estimar previamente o retorno do aumento das vendas de material original, para então verificar a viabilidade do investimento na animação.

Para a criação deste modelo, serão utilizadas como base as informações do My Anime List, disponíveis no Kaggle[2]. O My Anime List é um portal semelhante ao IMDb, onde diversos usuários (pessoas comuns e críticos especializados) podem publicar reviews de animes. Os dados estão em 3 conjuntos diferentes: registros de pessoas, de animes e de classificações.

Uma vez que os dados ultrapassam 12 GB em memória, o processamento para compilar o dataset de treinamento será feito em lotes e com arquivos .parquet. Em seguida, espera-se criar um modelo de classificação MLP por meio do PyTorch, que possui buffers capazes lidar melhor com particionamento e memória. Para a segmentação de público, o algoritmo K-Means do scikit-learn será utilizado. A avaliação de desempenho será por meio do F1-Score. A montagem do sistema final será feita por meio de um executável em Python, que entregará a interface de interação do usuário com a solução final.

[1] HARAGUCHI, Kazuya. The Anime Business Impact Index: Proposing a Measure to Assess Trends in the Japanese Anime Industry Using Social Network Analysis. The Japanese Journal of Animation Studies, v. 23, n. 2, 2022.

[2] KAGGLE. Anime Dataset 2023. Disponível em: https://www.kaggle.com/datasets/dbdmobile/myanimelist-dataset. Acesso em: 27 de outubro de 2024.

[3] PRAKASH, V.; RAGHAV, S.; SOOD, S.; PANDEY, M.; ARORA, M. Deep Anime Recommendation System: Recommending Anime Using Collaborative and Content-based Filtering. In: 2022 4th International Conference on Advances in Computing, Communication Control and Networking (ICAC3N), Greater Noida, Índia, 2022.

[4] RESWARA, C. G.; NICOLAS, J.; ANANTA, M.; KURNIADI, F. I. Anime Recommendation System Using Bert and Cosine Similarity. In: 2023 4th International Conference on Artificial Intelligence and Data Sciences (AiDAS), IPOH, Malásia, 2023.

[5] ZHAO, Haijing. Research on Marketing Strategies Used in Japanese Anime Industry Taking the Demon Slayer as an Example. Advances in Economics, Business and Management Research, v. 219, 2022.

# Fontes de dados

Este projeto utiliza 3 bases de dados diferentes para compor o conjunto de treinamento final, sendo elas:

- Descritivo de usuários cadastrados na plataforma (users-details-2023.csv);
- Descritivo dos animes existentes (anime-dataset-2023.csv);
- Registros de notas enviadas pelos usuários para diferentes animes (users-score-2023.csv).

Todas as bases estão disponíveis no Kaggle por meio deste [link](https://www.kaggle.com/datasets/dbdmobile/myanimelist-dataset), com os nomes demonstrados anteriormente entre parênteses.

# Contato

Bruno de Lima Santos

E-mail: bruno.19ls@gmail.com