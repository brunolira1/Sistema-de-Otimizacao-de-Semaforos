# INTRODUÇÃO E CONTEXTUALIZAÇÃO DO TEMA

Um dos maiores problemas das grandes cidades no mundo atual é a superlotação do fluxo de tráfego ao redor da cidade. Há uma quantidade extrema de veículos nas ruas e avenidas, o que causa enormes congestionamentos nas cidade. Um dos fatores que contribuem com o grande engarrafamento é a forma como os semáforos da cidade se comportam, muitas vezes de forma pouco inteligente.

O objetivo do nosso projeto é criar um sistema inteligente para controlar os semáforos de trânsito de um bairro. Esse sistema irá controlar o tempo em que cada semáforo alterna entre as fases verde / vermelho de forma que o fluxo de trânsito seja o mais otimizado possível na região. Dessa forma, possibilitando um trânsito mais justo e eficiente.

Neste sistema serão elaboradas técnicas de processamento de dados que serão extraídos a partir da criação de um simulador no qual irá representar vias de trânsito de um determinado local. Nossa simulação conta com uma série de aspectos relevantes, como a configuração de rotas de trânsito, velocidade máxima das pistas, densidade do trânsito, a fim de torna-lo o mais próximo da realidade possível. Em uma segunda etapa, descrita posteriormente, os dados apresentados durante as simulações serão utilizadas pelo nosso sistema para atribuir um valor discreto referente ao nível do fluxo de trânsito (quanto maior o valor, mais elevado o trânsito) que ocorre num determinado momento nas vias. Valor esse que será importante para o treinamento do nosso modelo.

Por meio desse formato, a forma com que nosso modelo busca otimizar o fluxo de trânsito é da redução ao máximo do tempo de espera médio dos veículos presentes na simulação.

O modelo será treinado por meio da técnica de aprendizado por reforço, um método que possibilita a interação entre um determinado agente e ambiente, no qual esse agente realiza ações no ambiente, e aprende de acordo com os resultados de suas ações. O objetivo desse agente é maximizar as recompensas totais que o ambiente pode oferecer. Falaremos mais detalhadamente sobre o aprendizado por reforço e como ele se encaixa no treinamento do nosso modelo no capítulo de Metodologia.

## PESQUISAS REFERENTES AO TEMA

Pesquisas indicam que o grande congestionamento de trânsito em grandes cidades atrapalham não apenas o tempo hábil de deslocamento dos cidadãos, como também interfere negativamente na economia das cidades como um todo. Em 2018, na cidade de Boston (Estados Unidos), por exemplo, estima-se que o congestionamento da cidade causou para os motoristas uma perda de 164 horas, em média, presos no trânsito, consequentemente causando uma perda econômica de 4,1 bilhões de dólares para a cidade. Além disso também há estudos que apontam que o extenso congestionamento afetam psicologicamente os motoristas, deixando-os mais estressados no dia a dia e com comportamentos mais agressivos.

No Brasil, pessoas economicamente ativas nas capitais gastam diariamente cerca de 64,5 minutos em média presas em congestionamentos segundo o SEBRAE.

Um dos principais fatores que contribuem para esse cenário é o fato de que a maioria dos semáforos espalhados pelo mundo ainda utilizam o método do ciclo fixo. Neste método, é calculado manualmente e previamente um tempo fixo para cada semáforo transitar entre os modos verde e vermelho. Entretanto, essa forma, utilizada desde o início do século XX, é considerada ineficiente e contribuinte para a superlotação no fluxo de trânsito. Recentemente, passou-se a perceber uma nova perspectiva na forma com que os semáforos de trânsito atuam, e a partir disso começou a haver vários estudos para a criação de semáforos que consigam agir de forma inteligente, visando a otimização do fluxo de trânsito ao redor das cidades.
