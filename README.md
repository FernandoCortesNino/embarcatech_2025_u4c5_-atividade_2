# O projeto de um sistema de temporização com acionamento único (One Shot) utilizando o microcontrolador Raspberry Pi Pico W e a função add_alarm_in_ms() do Pico SDK. O objetivo deste trabalho é demonstrar como um pushbutton pode acionar LEDs em sequência com temporização controlada, garantindo um funcionamento ordenado e eficiente. O projeto foi implementado e simulado no Wokwi e validado utilizando a ferramenta educacional BitDogLab.  O sistema é ativado quando o usuário pressiona um botão (pushbutton), acionando uma sequência de estados dos LEDs com atraso de 3 segundos entre cada mudança.

# O funcionamento segue os seguintes passos:
1) Pressionamento do botão: Todos os LEDs (azul, vermelho e verde) são acionados.
2) Primeira transição: Após 3 segundos, um dos LEDs é desligado.
3) Segunda transição: Após mais 3 segundos, apenas um LED permanece aceso.
4) Finalização: Após a última transição, todos os LEDs são desligados e o sistema pode ser reiniciado com um novo pressionamento do botão.
5) O botão só pode iniciar uma nova sequência após a finalização completa da rotina anterior, impedindo acionamentos repetidos durante a execução do temporizador.

# Configuração e Implementação
1) O código foi desenvolvido no VS Code utilizando o Pico SDK.
2) A simulação foi realizada no Wokwi, permitindo validar a lógica antes da implementação no hardware real.
3) No BitDogLab, o experimento foi realizado utilizando um LED RGB (GPIOs 11, 12 e 13) e um Botão A (GPIO 05).
4) Opcionalmente, foi implementada uma rotina de software debounce para minimizar os efeitos de bouncing do botão.

# Objetivos
1) Compreender o funcionamento de temporizadores de um disparo (One Shot) utilizando a função add_alarm_in_ms() do Pico SDK para o acionamento e controle de LEDs.
2) Implementar e analisar o uso de temporização programada, garantindo a alternância dos LEDs em intervalos predefinidos de 3 segundos.
3) Integrar o uso de botões (pushbutton) com microcontroladores, desenvolvendo um sistema que responda corretamente a eventos de entrada.
4) Explorar o conceito de funções de call-back para gerenciar mudanças de estado dos LEDs de forma controlada e eficiente.
5) Evitar múltiplas ativações indesejadas do botão durante o funcionamento do temporizador, garantindo que uma nova ativação ocorra apenas quando o ciclo de temporização for concluído.
6) Realizar experimentos no BitDogLab utilizando o LED RGB e o Botão A (GPIO 05) para validar a funcionalidade do sistema em um ambiente educacional.
7) Opcionalmente, implementar uma rotina de debounce em software, reduzindo os efeitos do bouncing do botão para melhorar a precisão da detecção de pressionamentos.

# Resultados Obtidos
A implementação do temporizador de um disparo (One Shot) utilizando a função add_alarm_in_ms() do Pico SDK foi realizada com sucesso, atingindo todos os objetivos propostos. Os principais resultados obtidos foram:

1) Funcionamento correto do temporizador: A ativação dos LEDs ocorreu conforme esperado, seguindo a sequência programada com um atraso de 3 segundos entre as mudanças de estado.
2) Resposta adequada ao acionamento do botão (pushbutton): O sistema respondeu corretamente ao pressionamento do botão, iniciando a sequência de ativação dos LEDs apenas quando o último LED já estivesse desligado.
3) Gerenciamento eficaz das transições dos LEDs: Os LEDs foram acionados e desligados na ordem programada, garantindo a transição de três LEDs acesos → dois LEDs acesos → um LED aceso → todos apagados.
4) Implementação bem-sucedida da call-back para controle dos LEDs: O uso da função de call-back permitiu a alternância dos estados dos LEDs sem necessidade de polling contínuo na rotina principal.
5) Prevenção de acionamentos múltiplos indevidos: Durante o funcionamento do temporizador, novos pressionamentos do botão não interferiram na execução da sequência de temporização, garantindo a robustez do sistema.
6) Testes no BitDogLab: O código foi validado com sucesso na placa BitDogLab, utilizando os GPIOs 11, 12 e 13 para o LED RGB e GPIO 05 para o botão A, demonstrando a viabilidade da implementação tanto na simulação quanto no hardware real.
7) Debounce (opcional): Quando implementada, a rotina de software debounce minimizou os efeitos do bouncing do botão, garantindo leituras mais confiáveis dos pressionamentos.
Esses resultados demonstram a efetividade da solução desenvolvida, consolidando o conhecimento sobre temporizadores, call-backs e manipulação de entradas e saídas no Raspberry Pi Pico W.


# Segue o link da atividade 2 : https://drive.google.com/file/d/19zxPgcGFfKjX7CeR7k0RvpNi5L7PNmvF/view?usp=sharing

# Conclusão
A implementação do sistema de temporização One Shot utilizando o Raspberry Pi Pico W demonstrou a aplicabilidade e eficácia do uso da função add_alarm_in_ms() para controle de eventos assíncronos. A estrutura do código garantiu a correta alternância dos estados dos LEDs, obedecendo ao tempo de atraso configurado e prevenindo acionamentos indevidos durante a execução da sequência.

Além disso, a restrição de acionamento do botão apenas após a conclusão do ciclo de temporização contribuiu para a robustez do sistema, evitando interrupções não desejadas. O teste realizado na ferramenta BitDogLab validou a funcionalidade do projeto tanto em ambiente simulado quanto em hardware real.

Por fim, a possível implementação de um software debounce aprimorou a confiabilidade da leitura do botão, reduzindo interferências causadas por bouncing. Dessa forma, a atividade reforçou conceitos essenciais de temporização, manipulação de GPIOs e programação de microcontroladores, proporcionando uma experiência prática valiosa para projetos futuros baseados no Pico SDK.



