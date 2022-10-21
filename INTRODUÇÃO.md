# INTRODUÇÃO E CONTEXTUALIZAÇÃO DO TEMA

Um dos maiores problemas das grandes cidades no mundo atual é a superlotação do fluxo de tráfego ao redor da cidade. Há uma quantidade extrema de veículos nas ruas e avenidas, o que causa um congestionamento gigante do trânsito da cidade. E um dos fatores que contribuem com o grande engarrafamento é a forma como os semáforos da cidade se comportam, muitas vezes de uma forma não inteligente.

Então, o objetivo do nosso projeto é criar um sistema inteligente e automatizado para controlar os sinais de trânsito de uma cidade. Esse sistema irá controlar o tempo em que cada semáforo alterna entre as fases verde / vermelho de forma que o fluxo de trânsito seja o mais otimizado possível na região. Dessa forma, possibilitando um trânsito mais justo e bem mais rentável.

Neste sistema será elaborado técnicas de processamento de imagem e a criação de um simulador de trânsito para extração de imagens em tempo real. Além de uma gama extensa de variáveis (comprimento e área do tráfego,largura da pista, densidade do trânsito...) que serão features utilizadas pelo nosso sistema para atribuir um valor entre 1 e 5 referente ao nível do fluxo de trânsito que ocorre num determinado momento em certa via. Iremos utilizar uma série de bibliotecas importadas na linguagem python, como o CV2 por exemplo (biblioteca voltada para treinamento de modelos de processamento de imagens).

A ideia é definir um temporizador otimizado para o sistema de semáforos, no qual seguirá a lógica de manter um semáforo mais tempo verde e pouco tempo vermelho numa via em que há um trânsito elevado, em comparação a semáforos próximos que estão localizados em vias menores, com trânsito menos extenso.
