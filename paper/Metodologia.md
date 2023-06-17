## INTRODUÇÃO AO CAPÍTULO DE METODOLOGIA

Como já dito no capítulo de introdução do tema, nosso objetivo é criar um sistema inteligente de controle de semáforos, que saiba otimizar o tempo de alternância
entre as fases verde/amarelo/vermelho de cada semáforo, de forma que o fluxo de trânsito de uma certa região seja o mais ideal possível. 
Nesse capítulo de metodologia iremos demonstrar de maneira aprofundada o passo a passo feito para construção desse sistema.

## TIPOLOGIA DE PESQUISA: 
Nesse tópico especificaremos os métodos que utilizamos para desenvolver nosso projeto, em termos de abordagem, pesquisa, fonte de dados e procedimentos.

A abordagem do projeto é do tipo quantitativa, pois realizamos uma análise objetiva com dados numéricos e gráficos para identificar os níveis de congestionamento presentes em determinada rua/avenida em um determinado instante.

Levando em conta os objetivos de pesquisa, nossa abordagem é do tipo exploratória, pois a pesquisa se baseia em um tema pouco explorado a nível global até o momento. Há muitas regiões ao redor do mundo que nunca implementaram sistemas de semáforos inteligentes em suas cidades, tampouco relataram pesquisas profundas sobre o assunto.

Em relação a fonte de dados a abordagem é do tipo laboratorial, pois estamos coletando nossos dados através de um simulador de trânsito (ambiente controlado) onde, apesar de determinados aspectos a respeito de sua estrutura serem definidos, as ações dos veículos são randômicas, a fim de aproximar o modelo simulado da realidade.

Por fim, levando em conta os procedimentos de pesquisa, desenvolvimento e conclusões que obtivemos, nossa abordagem é do tipo experimental, onde o objetivo de nosso trabalho se baseia em treinar e otimizar um modelo de sistema inteligente de semáforos de modo que, para alcançar resultados otimizados, é necessário realizar experimentos diversos e, com os dados produzidos pelas experimentações, influenciar, de forma positiva ou negativa, ações a serem realizadas.

## COLETA DE DADOS:

Neste projeto, foi criada uma simulação de semáforos utilizando o simulador SUMO (Simulation of Urban MObility).

O simulador SUMO (Simulation of Urban MObility) é uma ferramenta completa, aberta, e flexível para a simulação de tráfego urbano. Ele permite a criação de cenários complexos e realistas, considerando diferentes tipos de veículos, fluxos de tráfego e infraestrutura viária. Além disso, ele fornece uma ampla gama de informações e métricas para avaliar o desempenho do sistema de transporte, incluindo atrasos, tempos de viagem, consumo de combustível, emissões de poluentes, entre outros.

No entanto, neste projeto optamos por utilizar apenas carros e duas métricas principais para avaliar o desempenho do sistema de controle de semáforos: o tempo de espera e a quantidade de veículos em cada via. Essas métricas são consideradas importantes indicadores de desempenho para o controle de semáforos em cenários urbanos, pois ajudam a avaliar o congestionamento e o tempo de espera dos usuários. Ao utilizar essas métricas, nos aproximamos de um modelo real onde nosso modelo poderia atuar juntamente com modelos de visão computacional que podem fornecer esses dados em tempo real através câmeras posicionadas em semáforos.

Apesar de não utilizarmos todas as métricas disponíveis no SUMO, a ferramenta apresentou diversas vantagens para a simulação de tráfego urbano em nosso projeto. Uma dessas vantagens é a sua API Python que permite a integração com outras ferramentas e o desenvolvimento de algoritmos de aprendizado de máquina personalizados. Com a API Python do SUMO é possível criar scripts personalizados para a coleta de dados e avaliação do desempenho do sistema de controle de semáforos, como será apresentado a frente.

## TRATAMENTO E ANÁLISE DE DADOS:

Nossa simulação consiste em um cenário urbano formado por quatro cruzamentos interligados (S1, S2, S3 e S4). Os cruzamentos são formados por duas vias horizontais de três faixas cada (A e C) e duas vias verticais de duas faixas cada (B e D). Esse tipo de configuração é bastante comum em áreas urbanas onde o tráfego pode se tornar bastante intenso durante os horários de pico. 

A escolha desse tipo de configuração para nossa simulação se deve ao fato de que ela apresenta desafios interessantes para o controle de semáforos. Com várias ruas convergindo em cada cruzamento, é preciso ajustar os tempos de sinalização de forma adequada para garantir a fluidez do tráfego e evitar congestionamentos.

Além disso, definimos que a velocidade máximas das vias será de 40km/h (velocidade definida pelo Código de Trânsito Brasileiro - CTB para vias coletoras, como as simuladas) e os semáforos atuarão da seguinte forma: cada estágio amarelo terá duração fixa de 3 segundos e cada estágio verde/vermelho pode ter um valor variável entre 15 e 90 segundos. Essa faixa de duração é limitada devido a possível existência de pedestres atravessando ou aguardando para atravessar as vias

{figura 1}

Para gerar o tráfego de veículos nas ruas da simulação, utilizamos a configuração de "veículos por hora" em cada via. Essa configuração permite que definamos a quantidade de veículos que devem ser enviados por hora em cada via da simulação. Apesar do volume fixo de veículos por hora, a entrada deles na via é realizada de forma randômica. Buscando criar um modelo similar a realidade, levando em conta momentos de picos nas ruas, foi definido a quantidade de veículos da seguinte forma:

{figura 2}

Em nosso ambiente simulado, os veículos que por ele circulam possuem mais de uma rota de saída possível. Essa configuração é importante para que se reflita na simulação as condições reais de tráfego em determinada área. Cada veículo possui uma de quatro possíveis rotas, como mostrado na imagem abaixo (Figura 4). Essas rotas foram cuidadosamente escolhidas de forma a refletir as condições reais de tráfego na área simulada.

O fluxo de veículos nas duas vias de três faixas (A e C) é distribuído da seguinte forma: 10\% dos veículos viram na primeira direita, 66\% continuam em linha reta até o fim da via, 14\% viram na segunda esquerda e continuam em linha reta e os 10\% restante viram na segunda esquerda, depois viram na primeira esquerda e seguem em linha reta em direção contrária a que estavam no início do percurso.

{figura 3}

{figura 4}

Nas duas vias de duas faixas (B e D) o fluxo é distribuído da seguinte forma: 15\% dos veículos viram na primeira direita, 50\% continuam em linha reta até o fim da via, 20\% viram na segunda esquerda e continuam em linha reta e os 15\% restante viram na segunda esquerda, depois viram na primeira esquerda e seguem em linha reta em direção contrária a que estavam no início do percurso.

Para testar a eficácia do modelo, realizamos uma série de testes com os tempos dos semáforo definidos previamente, como é utilizado em grande parte do mundo atualmente, variando entre 15 e 90 segundos.

{figura 5}

Em semáforos com tempos definidos previamente, o melhor resultado nos testes simulados foi o de 15 segundos em cada estágio de verde/vermelho. Nesta configuração o tempo de espera médio dos carros que passaram pelo ambiente durante um dia completo foi de 11,28 segundos. Podemos observar a seguir os tempos de espera médio das vias de cada semáforo.

{figura 6}

{figura 7}

{figura 8}

{figura 9}


##APRENDIZADO POR REFORÇO

O aprendizado por reforço é uma abordagem de Inteligência Artificial em que um agente aprende a tomar decisões através de interações com um ambiente. Nesse processo, o agente recebe um feedback na forma de recompensas a cada ação tomada, com o objetivo de maximiza-la ao longo do tempo. Com base nas recompensas recebidas, o agente aprende a associar as ações aos melhores resultados a fim de tomar decisões mais acertadas no futuro.

Em nosso modelo, utilizaremos a abordagem para definir os tempos de cada estágio dos semáforos com base em interações com o ambiente simulado. Através dessa técnica o modelo será capaz de processar informações espaciais e temporais relevantes para o tráfego urbano, permitindo aprender padrões complexos e tomar decisões ótimas em tempo real.

Nesse contexto, as ações são as diferentes combinações de tempos de semáforo em que o modelo pode escolher (em nosso caso 15 a 90 segundos) e as recompensas são valores numéricos resultantes do tempo de espera e a quantidade de veículos em cada cruzamento após a realização de determinada ação.

A abordagem é ilustrada abaixo:

{figura 10}

O estado (S) é uma representação do ambiente em um determinado momento, no caso o inteiro mais próximo do resultado da quantidade total de veículos parados (qvp) dividido por 5.

A recompensa (R) é um valor numérico que indica a qualidade/desempenho de uma ação tomada pelo agente em um determinado momento (t) Seu valor consiste pelo inteiro mais próximo da adição de 10 ao tempo total de espera dos veículos (ttev) dividido pela quantidade total de veículos parados (qvp) vezes (-1) se (qvp) for maior que 0, senão 0.

Para o cálculo da ação (A), o tempo de duração dos estágios do semáforo, introduziremos uma nova variável em nosso modelo: o épsilon (ε). Seu valor é utilizado para controlar a taxa de exploração do agente durante o processo de escolha de ações. Épsilon é um parâmetro que determina a probabilidade de o agente realizar uma ação aleatória ao invés da escolha de uma ação de maior qualidade testada anteriormente. Inicialmente, definiremos seu valor como 0,7 e, a cada episódio, reduziremos seu valor gradualmente em 0,5%, permitindo que o agente confie mais nas estimativas presentes em seu banco de dados. Por fim, o valor da ação é definido da seguinte forma:

1. Se o valor de épsilon (ε) for maior que um valor aleatório (X) ou o estado (S) não estiver sido inicializado no banco de resultados, é escolhida uma ação aleatória entre as possíveis (15 a 90 segundos de tempo de esperado).
2. Senão, é escolhido o tempo de duração com melhor qualidade testado anteriormente.


{equação 1}

{equação 2}

{equação 3}

De forma simplificada, nosso modelo consiste em uma comunicação de mão dupla entre o agente (modelo definidor de tempos) e o ambiente (semáforos):

1. Analisando o ambiente, o agente envia uma ação para o ambiente (definir um tempo especifico para o estágio verde/vermelho do semáforo).
2. Após o ambiente realizar a ação (finalizar o estágio solicitado), é retornado para o agente dois valores resultantes: o estado (situação dos veículos nas vias ao final do processo) e a recompensa (qualidade da ação realizada).
3. O processo é iniciado novamente.

A final de cada ação realizada no contexto do aprendizado por reforço é realizado o cálculo e atualização dos valores Q. Os valores Q representam as estimativas da qualidade de uma ação em um determinado estado, indicando o valor esperado de recompensas futuras que podem ser alcançadas ao realizar essa ação.

Durante o teste o agente interage com o ambiente tomando ações com base na política de decisão estabelecida. Após realizar uma ação e observar o próximo estado e a recompensa recebida, o agente utiliza essas informações para atualizar o valor Q correspondente à ação tomada no estado anterior. Ações que resultaram em menor quantidade de carros parados resultam em melhores valores Q.

O cálculo do valor Q é realizado utilizando uma fórmula que combina a taxa de aprendizado α (alpha) com a recompensa imediata e o valor Q estimado do próximo estado, ponderada pelo fator de desconto γ (gamma). O fator de desconto é um parâmetro que indica a importância relativa das recompensas imediatas em comparação com as recompensas futuras.

Inicialmente, todos os valores Q são definidos como 0. A atualização do valor Q é realizada constantemente ao longo dos testes, permitindo ao agente refinar suas estimativas e melhorar a qualidade das ações tomadas. Conforme o agente continua a interagir com o ambiente e coletar mais experiências, os valores Q se aproximam dos valores ótimos, refletindo a ação que leva à maior recompensa esperada em cada estado.

{equação 4}
