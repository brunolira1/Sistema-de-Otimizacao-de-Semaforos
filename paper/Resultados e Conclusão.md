## Resultados finais e Conclusão

Para treinar o modelo de aprendizado por reforço no controle do tempo de semáforos utilizamos uma máquina virtual da Amazon Web Services (AWS), especificamente a instância Inf1. Essa máquina possui recursos otimizados para tarefas de inferência em aprendizado de máquina e foi escolhida devido à sua capacidade de processamento acelerado. 
Todos os parâmetros utilizados na versão satisfatória do modelo são apresentados Tabela 1 (abaixo). O treinamento completo simulou 200 episódios, ou seja, 200 dias completos, realizando 
testes e ajustes dos dados. O tempo de treinamento total foi de 3 horas e 52 minutos.

{tabela 1}

Durante o treino, observamos uma melhora constante dos resultados e um aumento contínuo das recompensas obtidas pelo modelo de aprendizado por reforço (Figura 11). Essa evolução gradual foi um indicativo claro de que os agentes estavam aprendendo a tomar decisões mais eficientes no controle do tempo de semáforos.

Conforme as iterações do treinamento prosseguiam, os agentes demonstraram uma maior capacidade de antecipação e adaptabilidade diante de diferentes situações de tráfego. Foram gerados 12 níveis de tráfego, variando desde o menor, representando menos veículos, até o maior, representando um fluxo mais intenso.

A habilidade dos agentes em identificar e responder adequadamente a diferentes níveis de tráfego é um dos pontos fortes da abordagem de aprendizado por reforço. Essa flexibilidade adaptativa permitiu que os agentes aprendessem a lidar com uma ampla gama de cenários de tráfego, preparando-os para enfrentar situações reais com eficiência e eficácia.


{figura 11}

Para cada um dos 12 níveis de tráfego, os agentes conseguiram alcançar valores ótimos na tabela Q, representando a aprendizagem das melhores ações a serem tomadas em cada estado bem-sucedida (Figura 12). Essa capacidade de adaptação e generalização é crucial para a eficácia do controle do tempo de semáforos, pois permite melhorias significativas na redução de congestionamentos, diminuição dos tempos de espera e otimização do uso das vias, independentemente do nível de tráfego enfrentado.

{figura 12}

Após o treinamento dos agentes de controle de semáforos utilizando o aprendizado por reforço, realizamos testes para avaliar o desempenho do modelo treinado. Os resultados foram impressionantes, com um tempo de espera médio total nos semáforos de apenas 5,79 segundos. Esse valor representa uma redução significativa de 48,7% em relação ao melhor resultado obtido nos testes com tempos fixos (11,28 segundos).

A comparação com os testes de tempos fixos é fundamental para validar a eficácia do modelo treinado. Os tempos fixos são baseados em padrões predefinidos e não são capazes de se adaptar às mudanças no tráfego em tempo real. No entanto, com o aprendizado por reforço, os agentes foram capazes de aprender a ajustar dinamicamente o tempo de abertura dos semáforos com base nas condições de tráfego em cada momento.

Abaixo é possível observar o tempo de espera médio nos semáforos. Comparando com o melhor resultado das simulações com tempos fixos, é possível observar uma grande melhora durante todos os períodos do dia, especialmente entre os com maior fluxo de veículos.


{figura 13}

{figura 14}

{figura 15}

{figura 16}

Os resultados obtidos neste projeto são altamente promissores e indicam a eficácia do uso de aprendizado por reforço para o controle do tempo de semáforos. A redução de 48,7% no tempo de espera médio total nos semáforos em comparação aos testes com tempos fixos é um indicativo claro da capacidade dos agentes treinados em otimizar o fluxo de veículos.

É importante ressaltar que os resultados obtidos nesse projeto não apenas demonstram a eficácia do aprendizado por reforço no controle do tempo de semáforos, mas também apontam para a necessidade de abordagens mais dinâmicas e adaptáveis nessa área. A gestão eficiente do tráfego urbano é fundamental para reduzir congestionamentos, minimizar o tempo de viagem dos usuários e promover uma mobilidade sustentável.

Embora esse projeto tenha alcançado resultados notáveis, é importante destacar algumas limitações e recomendações para trabalhos futuros. Por exemplo, é possível explorar a combinação de aprendizado por reforço com outras abordagens, como aprendizado supervisionado e redes neurais, para obter ainda melhores resultados. Além disso, é importante considerar a implementação prática desse modelo em um ambiente real, avaliando sua escalabilidade e interação com outros sistemas de controle de tráfego.

Um requisito essencial para a implementação efetiva do controle do tempo de semáforos através do aprendizado por reforço é a disponibilidade de dados precisos e em tempo real sobre o tráfego. Nesse sentido, a utilização de câmeras e algoritmos de visão computacional desempenha um papel fundamental. Essa tecnologia permite capturar imagens em tempo real das vias e, por meio de algoritmos avançados, processar essas imagens para extrair informações relevantes, como a contagem de veículos e seus estados nas vias. Essa tecnologia conta com pesquisas em estado avançado e sendo aplicada em algumas cidades ao redor do mundo. Além disso, outras tecnologias em desenvolvimento, como sensores ultrassônicos ou de visão dinâmica, se mostram capazes de fornecer os dados necessários com possíveis melhores resultados, devido a capacidade de funcionamento intermitente independente das condições meteorológicas das vias.

O texto foi elaborado por todos os autores em conjunto, como requisito para obtenção do título de Bacharel em Ciência de Dados e Inteligência Artificial pela Pontifícia Universidade Católica de São Paulo (PUC-SP), sob orientação do Prof. Dr. David de Oliveira Lemes.
