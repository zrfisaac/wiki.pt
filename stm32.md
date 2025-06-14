<!-- # [ zrfisaac ] -->

<!-- # [ about ] -->
<!-- # - author : Isaac Caires -->
<!-- # . - email : zrfisaac@gmail.com -->
<!-- # . - site : zrfisaac.github.io -->
<!-- # - version : zrfisaac.wiki.pt.base : 0.0.1 -->

<!-- # [ markdown ] -->
# STM32

## Descrição
STM32 é uma família de microcontroladores de 32 bits desenvolvida pela STMicroelectronics, baseada no núcleo ARM® Cortex®. Ela é amplamente utilizada em sistemas embarcados por sua performance, baixo consumo de energia e ampla variedade de periféricos integrados.

---

## Índice
- [Microcontroladores](#microcontroladores)
  - [CH32F103C8T6](#microcontroladores--ch32f103c8t6)

---

## [Microcontroladores](#índice)

### [Microcontroladores](#microcontroladores) > [CH32F103C8T6](#índice)

> [`Shopee`](https://shopee.com.br/STM32F103C8T6-CH32F103C8T6-ARM-STM32-Placa-De-Desenvolvimento-M%C3%ADnimo-Do-Sistema-STM32F401-STM32F411-Programador-De-Download-ST-LINK-V2-i.346512197.23596185431?sp_atk=61182dce-6245-4bdd-87a4-1e244150fa7b&xptdk=61182dce-6245-4bdd-87a4-1e244150fa7b)

O **CH32F103C8T6** é um microcontrolador de 32 bits da empresa **WCH (Nanjing Qinheng Microelectronics)**. Ele é altamente compatível com o **STM32F103C8T6**, sendo muito utilizado como substituto em placas como o **Blue Pill**, principalmente por seu **baixo custo**.

##### Resumo

| Item                   | Valor / Descrição                                                     |
| ---------------------- | --------------------------------------------------------------------- |
| **Núcleo**             | ARM® Cortex-M3                                                        |
| **Frequência**         | Até 72 MHz                                                            |
| **Memória Flash**      | 64 KB                                                                 |
| **SRAM (RAM)**         | 20 KB                                                                 |
| **GPIOs Totais**       | Até 37 pinos de uso geral (34 usados + 3 GND)                         |
| **Tensão de operação** | 2.0V a 3.6V                                                           |
| **Periféricos**        | UART, SPI, I2C, ADC, PWM, USB FS, CAN                                 |
| **Conversores ADC**    | 2 ADCs de 12 bits com múltiplos canais                                |
| **USB**                | Dispositivo USB Full-Speed (Device Only)                              |
| **Pacote físico**      | LQFP-48                                                               |
| **Programação**        | SWD (Serial Wire Debug), USB                                          |
| **GND (Terra)**        | 3 pinos – Essencial para o circuito funcionar                         |
| **3.3V**               | 2 pinos – Alimentação de sensores ou módulos                          |
| **5V**                 | 1 pino – Entrada principal de alimentação da placa                    |
| **RESET (R)**          | 1 pino – Reinicia o microcontrolador manualmente                      |
| **VBAT (VB)**          | 1 pino – Alimenta o RTC ou memória de backup                          |
| **Funções nos GPIOs**  | PWM, ADC, UART, SPI, I2C, CAN, USB, RTC, Debug (JTAG/SWD), LEDs, etc. |

##### ST-Link V2

| Pino no ST-Link | Nome do Sinal | Função                                                   | Conectar ao Pino do CH32F103C8T6  |
| --------------- | ------------- | -------------------------------------------------------- | --------------------------------- |
| 1               | 3.3V          | Alimenta o ST-Link ou detecta tensão de operação do alvo | 3.3V                              |
| 2               | SWDIO         | Linha de dados do debug SWD (entrada/saída)              | PA13 (ou pino marcado como SWIO)  |
| 3               | SWCLK         | Clock do debug SWD                                       | PA14 (ou pino marcado como SWCLK) |
| 4               | GND           | Terra comum entre o ST-Link e o microcontrolador         | GND                               |

##### Tabela de Pinos

| Nº | Pino | Descrição Curta                                                    |
| -- | ---- | ------------------------------------------------------------------ |
| 1  | G    | GND – Terra elétrica comum para todo o circuito                    |
| 2  | G    | GND – Terra elétrica (redundante para facilitar conexão)           |
| 3  | 3.3  | Saída de 3.3V – Alimentação de sensores ou módulos de 3.3V         |
| 4  | R    | RESET – Reinicia o microcontrolador manualmente                    |
| 5  | B11  | I2C2 SDA / PWM – Comunicação I2C ou saída PWM                      |
| 6  | B10  | I2C2 SCL / PWM – Comunicação I2C ou saída PWM                      |
| 7  | B1   | ADC / PWM – Entrada analógica ou saída PWM                         |
| 8  | B0   | ADC / PWM – Entrada analógica ou saída PWM                         |
| 9  | A7   | ADC / PWM – Entrada analógica ou controle de motor                 |
| 10 | A6   | ADC / PWM – Entrada analógica ou controle de motor                 |
| 11 | A5   | SPI1 SCK – Comunicação SPI (clock) ou entrada analógica            |
| 12 | A4   | SPI1 MISO – Comunicação SPI (dados recebidos) ou entrada analógica |
| 13 | A3   | SPI1 MOSI – Comunicação SPI (dados enviados) ou entrada analógica  |
| 14 | A2   | ADC – Entrada analógica                                            |
| 15 | A1   | ADC – Entrada analógica                                            |
| 16 | A0   | ADC – Entrada analógica                                            |
| 17 | C15  | OSC32\_OUT – Saída de oscilador de 32 kHz para RTC                 |
| 18 | C14  | OSC32\_IN – Entrada de oscilador de 32 kHz para RTC                |
| 19 | C13  | GPIO / LED – Usado com frequência para LED onboard                 |
| 20 | VB   | VBAT – Alimentação para RTC ou dados em backup                     |
| 21 | B12  | SPI2 NSS – Comunicação SPI / controle de motor                     |
| 22 | B13  | SPI2 SCK – Comunicação SPI (clock)                                 |
| 23 | B14  | SPI2 MISO – Comunicação SPI (dados recebidos)                      |
| 24 | B15  | SPI2 MOSI – Comunicação SPI (dados enviados)                       |
| 25 | A8   | PWM / USART1\_CK – Saída PWM ou clock da UART                      |
| 26 | A9   | USART1 TX – Transmissão serial (UART)                              |
| 27 | A10  | USART1 RX – Recepção serial (UART)                                 |
| 28 | A11  | USB DM / CAN RX – Comunicação USB ou CAN                           |
| 29 | A12  | USB DP / CAN TX – Comunicação USB ou CAN                           |
| 30 | A15  | SPI1 NSS / JTAG – Comunicação SPI ou debug                         |
| 31 | B3   | JTAG / PWM – Depuração ou saída PWM                                |
| 32 | B4   | PWM / JTAG – Saída PWM ou função de debug                          |
| 33 | B5   | PWM / I2C1 SMBA – Saída PWM ou barramento I2C                      |
| 34 | B6   | I2C1 SCL / PWM – Comunicação I2C ou saída PWM                      |
| 35 | B7   | I2C1 SDA / PWM – Comunicação I2C ou saída PWM                      |
| 36 | B8   | CAN RX / PWM – Comunicação CAN ou saída PWM                        |
| 37 | B9   | CAN TX / PWM – Comunicação CAN ou saída PWM                        |
| 38 | 5V   | Entrada de 5V – Alimenta o regulador da placa                      |
| 39 | G    | GND – Terra elétrica (mais um ponto de conexão)                    |
| 40 | 3.3  | 3.3V – Saída regulada ou entrada para lógica                       |
