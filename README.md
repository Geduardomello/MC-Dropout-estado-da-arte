# MC-Dropout-estado-da-arte
MONTE CARLO DROPOUT
Replicação do estado da arte
Incerteza Epistêmica em Redes Neurais - Gerson Eduardo de Mello

Esta é uma replicação de uma publicação de Matheus Facure em Outubro de 22 na página do LAMFO ( LAMFO - Laboratório de Aprendizado de Máquina em Finanças e Organizações) da universidade de Brasília ( UnB ) https://lamfo-unb.github.io/2017/10/22/Monte-Carlo-Dropout/ . Nesta publicação ele apresenta a técnica de Monte Carlo Dropout proposta por por Yarin Gal . O código do post é esse: https://github.com/matheusfacure/Tutoriais-de-AM/blob/master/Redes%20Neurais%20Artificiais/Bayesian-NN/BNN-Regression.ipynb

#Descrição do método proposto por Yarin Gal:

Em 2015, Yarin Gal mostrou que é possível obter incerteza a partir de redes neurais quase que gratuitamente, se olhássemos técnicas de regularização estocásticas, como Dropout, sob uma perspectiva Bayesiana. Dropout (Srivastava et al, ‎2014) é uma técnica utilizada na maioria das redes neurais modernas para prevenir sobre-ajustamento. Durante o treinamento, Dropout funciona zerando aleatoriamente uma percentagens de neurônios nas camadas da rede neural. No momento de fazer previsões, todos os neurônios são mantidos e a rede neural atua como uma grande mistura de sub-redes menores. Durante o treinamento do modelo, nada muda; mas, durante o teste mantemos a probabilidade de Dropout fixada durante o treino e realizamos T forward-pass pela rede, coletando assim T previsões y para cada amostra. Assim para cada ponto teremos uma previsão para a média e uma previsão para a variância, que será nossa medida de incerteza.

Obs: Foram necessáris duas correções que no código original estavam erradas:

linha 61- label "prevista " e "real" estavam incertidas

linha 67 substituição do código: for shade in range(1, 5): plt.fill_between(t, mu, mu-sigma * (.5shade), alpha=0.2, color="C2") pelo código: for shade in range(1, 5): plt.fill_between(t, mu+sigma (.5shade), mu-sigma * (.5shade), alpha=0.2, color="C2")
