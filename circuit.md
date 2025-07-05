<!-- # [ zrfisaac ] -->

<!-- # [ about ] -->
<!-- # - author : Isaac Caires -->
<!-- # . - email : zrfisaac@gmail.com -->
<!-- # . - site : zrfisaac.github.io -->
<!-- # - version : zrfisaac.wiki.pt.base : 25.6.14.1 -->

<!-- # [ markdown ] -->
# Circuito

## Descrição
Um circuito eletrônico é uma interligação de componentes elétricos que permite o fluxo de corrente elétrica para realizar funções específicas — como acender um LED, amplificar som, armazenar energia ou gerar sinais de controle.

Esses circuitos são compostos por componentes ativos e passivos, conectados por fios ou trilhas condutoras, alimentados por uma fonte de energia (como uma bateria ou fonte de tensão).

---

## Índice
- [Componentes](#componentes)

---

## [Componentes](#índice)

| Componente                  | Símbolo Mermaid | Função                                                                 | Exemplo de Uso                                        |
| --------------------------- | --------------- | ---------------------------------------------------------------------- | ----------------------------------------------------- |
| 🔋 Bateria                  | `Bat`           | Fornece energia ao circuito.                                           | Alimentar circuitos com 3V, 5V ou 12V.                |
| 🔧 Resistor                 | `Res`           | Limita a corrente elétrica.                                            | Proteger LEDs, ajustar ganho de amplificadores.       |
| ⚡ Capacitor                | `Cap`           | Armazena e libera carga elétrica.                                      | Filtro em fontes de alimentação, temporizadores.      |
| 🔄 Indutor                  | `Ind`           | Armazena energia em campo magnético.                                   | Em fontes chaveadas e filtros de ruído.               |
| 🔮 Oscilador                | `Cry`           | Gera sinais de frequência constante.                                   | Clocks de microcontroladores (ex: 16MHz).             |
| 💡 LED                       | `Led`           | Emite luz quando recebe corrente.                                      | Indicadores visuais em placas e painéis.              |
| 🌎 Terra                    | `Gnd`           | Referência de 0V para o circuito.                                      | Toda malha negativa se conecta aqui.                  |
| 🔘 Botão                    | `Btn`           | Permite ou interrompe o fluxo de corrente manualmente.                 | Ligar/desligar dispositivos ou enviar sinais.         |
| 🧲 Diodo                    | `Dio`           | Permite corrente em uma só direção.                                    | Proteção contra polaridade reversa, retificação.      |
| ⚙️ Circuito Integrado       | `IC`            | Componente digital integrado; pode conter flip-flops, contadores, etc. | Controle de estado, memória, sincronização de sinais. |
| 🔁 Transistor NPN           | `Qnpn`          | Amplifica ou comuta sinais elétricos.                                  | Controle de carga, drivers de motores e LEDs.         |
| 🔂 Transistor PNP           | `Qpnp`          | Variante do transistor que conduz quando base está negativa.           | Amplificadores, controle de potência.                 |
| 🧠 Porta AND                | `And`           | Saída é alta apenas se todas as entradas forem altas.                  | Lógica digital, somadores binários.                   |
| 🔀 Porta OR                 | `Or`            | Saída é alta se pelo menos uma entrada for alta.                       | Comparadores lógicos, controle de eventos.            |
| ⛔ Porta NOT (Inversor)     | `Not`           | Inverte o sinal de entrada.                                            | Osciladores, inversores lógicos.                      |
| 📦 Registrador              | `Reg`           | Armazena temporariamente dados binários.                               | CPUs, pipelines, buffers.                             |
| 🕒 Flip-Flop D              | `DFF`           | Armazena um bit de dado na borda do clock.                             | Memória de 1 bit, controle de estado.                 |
| 🔉 Buzzer                   | `Buzz`          | Emite som quando ativado.                                              | Alarmes, sinais sonoros.                              |
| 🌡️ Termistor                 | `Therm`         | Resistor que varia com a temperatura.                                  | Sensores de temperatura, proteção térmica.            |
| 📏 Potenciômetro            | `Pot`           | Resistor ajustável manualmente.                                   | Controle de volume, ajuste de contraste.           |
| 📶 Antena                   | `Ant`           | Transmite ou recebe ondas eletromagnéticas.                       | Comunicação sem fio (RFID, Wi-Fi, Bluetooth).      |
| 🔁 Relé                     | `Relay`         | Comutador eletromecânico controlado eletricamente.                | Acionamento de cargas com alta corrente.           |
| 📄 Display LCD              | `LCD`           | Mostra caracteres ou gráficos em telas.                           | Interfaces de usuário em sistemas embarcados.      |
| 🧠 Microcontrolador (MCU)   | `MCU`           | Chip com CPU, memória e periféricos integrados.                   | Arduino, ESP32, automação e controle embarcado.    |
| 🧮 Contador                 | `Cnt`           | Contador digital de pulsos ou eventos.                            | Relógios digitais, medidores, contadores binários. |
| 🔢 Multiplexador            | `Mux`           | Seleciona uma entre várias entradas para uma única saída.         | Comunicação de dados, economizar pinos de I/O.     |
| 🔠 Decoder BCD              | `BCD`           | Converte código binário para decimal ou display de 7 segmentos.   | Contadores com saída visual.                       |
| 🔀 Shift Register           | `ShiftReg`      | Desloca bits de entrada serialmente e os apresenta paralelamente. | Expansão de saídas digitais em microcontroladores. |
| 💾 EEPROM / Memória         | `ROM`           | Armazena dados mesmo sem energia.                                 | Armazenamento permanente de configurações.         |
| 🌀 Sensor Hall              | `Hall`          | Detecta campo magnético.                                          | Sensores de velocidade, detectores de proximidade. |
| 💧 Sensor de Umidade         | `Hum`           | Detecta níveis de umidade no ambiente.                            | Agricultura, automação residencial.                |
| 🌞 Sensor de Luz (LDR)      | `LDR`           | Varia resistência conforme a luz incidente.                       | Acionamento automático de lâmpadas.                |
| 🌪️ Ventoinha / Fan          | `Fan`           | Gera fluxo de ar para resfriamento.                               | Refrigeração de fontes e processadores.            |
| 🔗 Conector / Header        | `Conn`          | Permite ligação física entre diferentes placas ou dispositivos.   | Jumpers, barramentos, pinos de I/O.                |
