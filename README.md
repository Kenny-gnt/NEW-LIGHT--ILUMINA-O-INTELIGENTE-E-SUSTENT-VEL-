# NEW-LIGHT--ILUMINA-O-INTELIGENTE-E-SUSTENTAVEL-

# O projeto New Light foi desenvolvido com o objetivo de aplicar conceitos de automação e sustentabilidade por meio da programação com Arduino. A proposta busca solucionar um problema comum do dia a dia: o desperdício de energia elétrica causado por luzes que permanecem acesas sem necessidade. Com o uso de sensores e lógica programada, o sistema consegue controlar automaticamente a iluminação, tornando o ambiente mais eficiente e econômico.

----------------------------------------------------------

# COMO FUNCIONA

O sistema monitora o ambiente utilizando dois sensores:
- Sensor PIR (Infravermelho Passivo): detecta a presença ou movimento de pessoas.

- Sensor LDR (Fotoresistor): mede o nível de luminosidade do ambiente.

O Arduino UNO interpreta essas informações e decide quando acender ou apagar a luz (simulada por um LED).
O comportamento segue a seguinte lógica:
 
- Se o ambiente estiver escuro e houver movimento, o LED é ligado.

- Se não houver presença ou o ambiente estiver claro, o LED é desligado.

Durante a execução, o sistema envia dados como tempo, níveis de luminosidade e estado do LED para o Serial Monitor, permitindo registrar e analisar o comportamento da automação.

----------------------------------------------------------
# TECNOLOGIAS UTILIZADAS

- Arduino UNO — microcontrolador central do sistema.

- Sensor PIR — responsável pela detecção de movimento.

- Sensor LDR — mede a intensidade da luz ambiente.

- LED — representa a lâmpada controlada pelo sistema.

- Simulador Wokwi — utilizado para montar e testar o circuito virtualmente.

- Python (Pandas) — usado para analisar os dados gerados pela simulação e calcular consumo, economia e emissão de CO₂ evitada.

----------------------------------------------------------

# ORIENTAÇÃO DE EXECUÇÃO

Esta seção explica exatamente como executar o projeto, desde a simulação do circuito no Wokwi até a análise dos dados no Python.
Mesmo quem nunca usou Arduino consegue seguir sem dificuldade.

# 1. Acessar a simulação no Wokwi

1. Entre no link do projeto (ou abra o arquivo diagram.json + sketch.ino no Wokwi).

2. Você verá o circuito montado com:

- Arduino Uno

- Sensor PIR

- Sensor LDR

- LED + resistor

3. Clique no botão “Start Simulation” (botão verde de Play)

# 2. Interagir com os sensores no Wokwi

Durante a simulação, você pode testar o funcionamento mexendo nos sensores:

SIMULAR DETECÇÃO DE MOVIMENTO (PIR)

- Clique em cima do sensor PIR.

- Mude o campo “State” para “motion detected”.

- Isso simula alguém entrando no ambiente.

SIMULAR ALTERAÇÃO NA LUMINISIDADE (LDR)

- Clique na lâmpada ao lado do LDR.

- Arraste o controle para (+) ou (–) para escurecer ou clarear o ambiente.

O LED DEVE RESPONDER AUTOMATICAMENTE SEGUINDO A LÓGICA

- Movimento + ambiente escuro → LED acende

- Sem movimento por alguns segundos → LED desliga

- Ambiente claro → LED permanece apagado

# 3. Acompanhar os dados no Serial Monitor

1. Clique em “Serial Monitor” na parte superior direita.

2. O sistema vai gerar linhas com a estrutura:

timestamp_ms,pir,ldr,led
3500,1,720,1
4800,0,820,0

# 4. Gerar o arquivo de log

Copiar direto do Serial Monitor

1. Selecione todas as linhas.

2. Cole em um arquivo chamado log.csv no seu computador.

# 5. Executar a análise dos dados (Python)

pip install pandas

# 5.1 Estrutura de arquivos

Crie uma pasta assim:

/projeto-iluminacao/
  log.csv
  analise.py

O arquivo analise.py deve estar no mesmo diretório do log.csv.
Se estiver em pastas diferentes, o script não encontra o arquivo.

# 5.2 Rodar o script

No terminal, dentro da pasta do projeto:

python analise.py

- Se rodar certo, você verá resultados como:

Tempo total da simulação: 25.3 s  
Tempo com luz acesa: 5.9 s  
Consumo estimado: 0.002 Wh  
Economia potencial: 78%  
CO2 evitado: 0.0011 g

Esses valores mostram se o sistema está economizando energia ou não.

# 6. Interpretar os resultados

O que cada cálculo significa:

- Tempo com luz acesa → quanto tempo o LED ficou ligado de verdade

- Consumo estimado → gasto total aproximado do LED

- Economia potencial → quanto teria sido gasto sem automação

- CO₂ evitado → impacto ambiental direto

 Assim é possível visualizar, de forma prática, o impacto da automação no uso eficiente de energia elétrica.

----------------------------------------------------------

# VIDEO
https://youtu.be/aKDQQKuJfvQ?si=s6nFaqnL33_4pyir

----------------------------------------------------------

# WOKWI
https://wokwi.com/projects/447330973862849537
