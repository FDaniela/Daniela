# CicloExergame v.1.0

O termo "CicloExergame" se refere a uma combinação entre um exergame e um cicloergometro. Um exergame é um tipo de jogo eletrônico que combina elementos de entretenimento digital com exercícios físicos. É uma forma de atividade física interativa que requer movimentos corporais por parte do jogador para interagir com o jogo.

Nesse contexto, o CicloExergame é um sistema desenvolvido com o uso de realidade virtual não imersiva e tem como objetivo potencializar as sessões de reabilitação, engajando os pacientes durante o tratamento. O protótipo desenvolvido inclui funcionalidades de comunicação, permitindo até mesmo a realização de sessões de reabilitação remotamente.

## Protótipo

O CicloExergame é composto por um hardware e um software específicos. No que diz respeito ao hardware, o CicloExergame é baseado em um cicloergômetro, que foi adaptado para integrar o sistema conectando o interruptor magnético do próprio aparelho, que é responsável pela contagem de ciclos de pedaladas, a uma placa [Arduino Uno](https://docs.arduino.cc/hardware/uno-rev3). Além disso, foram adicionados dois sensores para monitoramento do paciente: um para medir a frequência cardíaca (BPM) e outro para medir a oxigenação do sangue (SpO2). Esses [sensores](https://www.analog.com/media/en/technical-documentation/data-sheets/MAX30100.pdf) foram conectados à mesma placa Arduino Uno, e foram utilizadas modelagens para impressão 3D a fim de criar recipientes que protegem as placas e sensores contra desgastes e partículas do ambiente. Uma caixa adaptada para a placa Arduino foi fixada ao aparelho com abraçadeiras, e um protetor de dedo foi criado para os sensores que entram em contato com o dedo do paciente.

Em relação ao software, foi desenvolvido um jogo baseado no subgênero de jogos eletrônicos de plataforma chamado "endless runner" (corrida infinita). A mecânica desse jogo foi construída no motor de jogos [Unreal Engine 4](https://www.unrealengine.com/en-US/?state=%2F4.26%2Fen-US%2F), utilizando uma arquitetura cliente-servidor para o modo multiplayer. O sistema de "Blueprints Visual Scripting" foi utilizado para criar os elementos do jogo por meio de uma interface baseada em nós. O middleware responsável pela captura, processamento e transmissão de dados dos sensores foi conectado ao motor como um plugin externo, permitindo a integração dos dados coletados no jogo.

![ciclo](https://github.com/FDaniela/CicloExergame-1.0/assets/102395421/8b1ad6bc-2440-4575-b836-96692d95f2ea)


## Funcionamento

No CicloExergame, antes de iniciar a atividade, o fisioterapeuta realiza as configurações necessárias. Isso inclui definir os intervalos mínimos e máximos aceitáveis para os batimentos cardíacos e a saturação de oxigênio (SpO2), a duração da sessão, o modo de jogo (espectador ou jogador), a velocidade e a qualidade gráfica da sessão, além de habilitar ou desabilitar a presença de obstáculos e moedas. Essas configurações são enviadas ao servidor, que, por sua vez, envia ao paciente a ativação do botão "Play" para iniciar a atividade. O fisioterapeuta também pode modificar as configurações mesmo depois de a sessão ter começado em tepo real.

O paciente, antes de iniciar a atividade, precisa configurar a porta serial do Arduino em que o aparelho está conectado (geralmente COM4), bem como ajustar a qualidade gráfica adequada para o dispositivo que está utilizando. Após essas etapas, o jogo começa a ser executado.

Durante a atividade, um avatar montado em uma bicicleta é exibido no centro da tela, avançando de acordo com as pedaladas do paciente. A tela também apresenta HUDs (heads-up display) que mostram informações relevantes, como o número de moedas coletadas, a quantidade de pedaladas, a velocidade das pedaladas, os batimentos cardíacos e a saturação de oxigênio. Além disso, há alertas temporários, como o cumprimento de metas, que são exibidos na tela. O objetivo do paciente é percorrer o trajeto definido, desviando-se dos obstáculos (de acordo com a configuração estabelecida), coletando o maior número possível de moedas durante o tempo estipulado e mantendo a faixa de velocidade de pedaladas desejada.

O fisioterapeuta pode interagir com o jogo e o paciente de duas maneiras: no modo espectador ou no modo jogador. No modo espectador, o fisioterapeuta acompanha a atividade em uma visão de terceira pessoa, com o avatar do paciente ao fundo. São exibidos HUDs que apresentam a evolução cardiorrespiratória do paciente, juntamente com caixas contendo as configurações ajustadas no início da atividade, que podem ser modificadas, se necessário, para se adequarem à dificuldade esperada com base no desempenho do paciente. O outro modo é o de jogador, no qual o fisioterapeuta interage com um avatar jogável semelhante ao do paciente, podendo jogar junto com ele para proporcionar uma sensação de companhia e maior engajamento do paciente durante a reabilitação.

Ao final da sessão, a mesma tela é apresentada tanto para o paciente quanto para o fisioterapeuta. Ela exibe um gráfico que representa toda a evolução do desempenho cardiorrespiratório (batimentos cardíacos e oximetria) calculado durante a atividade. Esse gráfico proporciona uma avaliação clínica que pode ser armazenada e comparada com outras sessões gravadas, auxiliando na análise do progresso do paciente.

![telajogo](https://github.com/FDaniela/CicloExergame-1.0/assets/102395421/0a6c5f8f-6fa0-4ffb-b04c-a3ffaefc7cd0)

### Produções

1. [1º lugar no Concurso de Trabalhos de Iniciação Científica do Simpósio Brasileiro de Computação Aplicada à Saúde (CTIC-SBCAS 2023)](https://sol.sbc.org.br/index.php/sbcas_estendido/article/view/25330)
2. [19º Congresso de Pesquisa, Ensino e Extensão (CONPEEX) - #350](https://anaisconpeex.ciar.ufg.br/edicoes/19/index.html)
3. [Avaliação de um jogo digital para a telerreabilitação de pacientes - SEB](https://zenodo.org/record/7492216)
5. [A Serious Games and Game Elements Based Approach for Patient Telerehabilitation Contexts](https://sol.sbc.org.br/journals/index.php/jis/article/view/2679)
6. Distributed exergame with cycle ergometer for patient rehabilitation and engagement generation at telerehabilitation contexts
7. Jogos Sérios e Elementos de Jogos na Promoção de Engajamento em Contextos de Telerreabilitação de Pacientes
8. A Distributed Exergame for Telerehabilitation: An Engaging Alternative to Improve Patients’ Quality of Life
9. Jogos Digitais e Engajamento na Reabilitação de Pacientes: Uma Revisão Sistemática da Literatura
10. Exergame com Cicloergômetro para a Reabilitação de Pacientes em Tempos de COVID-19
