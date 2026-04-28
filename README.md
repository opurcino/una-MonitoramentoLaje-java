# Sistema SafeBuild: Monitoramento de Laje

## Descrição
O **Monitoramento de Laje** é uma aplicação de linha de comando desenvolvida em Java para o sistema *SafeBuild*. Ele simula o monitoramento de carga sobre uma laje durante atividades de construção (como concretagem). O objetivo é garantir a segurança dos trabalhadores, recebendo a leitura atual do sensor de carga e emitindo alertas e decisões de segurança com base na carga de projeto.

## Regras de Negócio e Alertas
O sistema utiliza uma carga de projeto definida em `15.0 kN/m²` e calcula os seguintes limites de segurança:

* 🟢 **Status VERDE (Seguro):** Carga atual abaixo da margem de segurança (menos de 80% da carga de projeto). 
    * *Ação:* Operação normal permitida.
* 🟡 **Status AMARELO (Alerta):** Carga atual atingiu a margem de segurança (entre 80% e 100% da carga de projeto).
    * *Ação:* Reduzir a velocidade de concretagem e evacuar pessoal não essencial.
* 🔴 **Status VERMELHO (Crítico):** Carga atual ultrapassou a carga de projeto (acima de 100%).
    * *Ação:* Interromper a obra imediatamente pelo risco de colapso.
    * 🚨 **ALERTA ADICIONAL:** Se a carga exceder 120% do projeto, é emitido um aviso de falha catastrófica iminente, exigindo evacuação total da área.

## Tecnologias Utilizadas
* **Java**: Linguagem principal.
* **java.util.Scanner**: Para captura da entrada de dados do usuário via terminal.

## Como Executar

1. Certifique-se de ter o **Java Development Kit (JDK)** instalado na sua máquina.
2. Salve o código fornecido em um arquivo chamado `MonitoramentoLaje.java`.
3. Abra o terminal (ou prompt de comando) e navegue até o diretório onde o arquivo foi salvo.
4. Compile o código com o comando abaixo:
   > `javac MonitoramentoLaje.java`
5. Execute a aplicação com o comando:
   > `java MonitoramentoLaje`
6. Quando solicitado, insira o valor da carga atual em kN/m² e pressione **Enter** para ver o status e a decisão do sistema. *(Atenção: dependendo do idioma do seu sistema operacional, a separação decimal deve ser feita com vírgula ou ponto).*
