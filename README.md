# Sprint01-COAA-EQUIPE1-1CCPW
Sistema Inteligente de Monitoramento e Controle de Carga para Eletropostos
Integrantes

Equipe 1 – 1CCPW

Lucca Bertolini — RM: 569552

Diego de Oliveira Brandão — RM: 569773

Raphaello Caffettani — RM: 572334

Cristhian Henrique Clementino — RM: 574117

Fabio Pena Vieira — RM: 570441

-

PROBLEMA

O crescimento da mobilidade elétrica aumenta a necessidade de sistemas de carregamento mais eficientes. No entanto, muitos eletropostos usam processamento computacional excessivo para executar tarefas simples, como leitura de sensores, monitoramento da bateria e controle do carregamento. Esse processamento desnecessário gera maior consumo energético, aumento de ciclos de CPU e redução da eficiência operacional.

-

JUSTIFICATIVA

Com o aumento do uso de veículos elétricos, pequenas perdas de processamento em cada estação de carregamento podem gerar grande impacto quando multiplicadas em uma escala larga. Dessa forma, torna-se necessário desenvolver soluções capazes de reduzir o consumo computacional e otimizar a utilização dos recursos do sistema, tornando os eletropostos mais eficientes e sustentáveis.

-

PROPOSTA DE SOLUÇÃO

A proposta consiste no desenvolvimento de um sistema inteligente de monitoramento e controle de carga utilizando sistemas embarcados e instruções Assembly.

-

O SISTEMA REALIZA:

-Monitoramento contínuo da corrente elétrica;
-Leitura do status da bateria;
-Controle automático do relé de carga;
-Interrupção automática em situações de risco;
-Operação otimizada com menor utilização de recursos computacionais.

A solução busca reduzir processamento desnecessário, aumentar a eficiência energética e garantir maior segurança durante o carregamento.

-

ARQUITETURA UTILIZADA

RISC (Reduced Instruction Set Computer).

-

CARACTERÍSTICAS PRINCIPAIS:

-Menor quantidade de instruções;
-Menos ciclos de clock;
-Execução mais rápida;
-Menor consumo energético;
-Melhor desempenho em sistemas embarcados.

TAMBÉM FORAM UTILIZADOS CONCEITOS DE:

-Pipeline;
-Ciclos de clock;
-Memória mapeada;
-Sistemas embarcados;
-Programação Assembly.

-

TRECHOS DE CÓDIGO ASSEMBLY

.data
ADDR_SENSOR_CORRENTE: .word 0x10000000
ADDR_STATUS_BATERIA:  .word 0x10000004
ADDR_RELE_CARGA:      .word 0x10000008

.text
.globl main

main:
    lw s0, ADDR_SENSOR_CORRENTE
    lw s1, ADDR_STATUS_BATERIA
    lw s2, ADDR_RELE_CARGA

    li t0, 1
    sw t0, 0(s2)

loop_monitoramento:
    lw t1, 0(s0)
    lw t2, 0(s1)

    li t3, 32000
    blt t3, t1, desligar_carga

    li t4, 100
    beq t2, t4, desligar_carga

    j loop_monitoramento

desligar_carga:
    li t0, 0
    sw t0, 0(s2)

fim:
    j fim

-
    
IMPACTOS ESPERADOS
Espera-se que a solução proporcione:

-Redução do consumo computacional;
-Menor gasto energético;
-Maior eficiência operacional;
-Monitoramento em tempo real;
-Maior segurança durante o carregamento;
-Melhor aproveitamento dos recursos do sistema.
-Relação com sustentabilidade e energias renováveis


A proposta contribui diretamente para a sustentabilidade ao reduzir desperdícios computacionais e otimizar o consumo de energia nos eletropostos.

-

Além disso, sistemas mais eficientes podem ser integrados a fontes renováveis, como:

-Energia solar;
-Energia eólica;
-Redes inteligentes (Smart Grid).

Com isso, a solução auxilia na redução dos impactos ambientais e promove o uso mais sustentável da mobilidade elétrica.
