# Projeto-Roomba

Olá, voce que esta lendo esse repositorio suponho que se trate de um estudante do IFPR Campus Pinhais que recebeu este robo para seu projeto de TCC

Acredito que o robo que voce recebeu se tem uma Raspberry PI e um Arduino conectados ao mesmo, Bom foi nosso grupo de TCC com ajuda de nosso orientador que os colocaram ali.
Eles estão ali especialmente para que voce e seu grupo agora possam ja saltarem grandes passos para seu projeto indepedente de qual for, este repositorio possue algumas dicas e guias
para caso seja nescessario e assim ajudar mais do que ja ajudamos no seu trabalho :) 
# Inicialização Automatica 

(...)

# Alteração do Codigo Arduino

Com muito cuidado, conecte seu Arduino a um computador via um cabo USB A/B, então acesse o Arduino IDE, o arquivo "Create Test" que voce pode encontrar neste repositorio deve conter o codigo que
esta presente no seu Arduino no momento que voce recebe-lo, é recomendado que voce use-o como base e/ou o salve como um backup. Este arquivo contem as configurações de movimentação de seu Roomba, 
com o controle e velocidade de ambas as rodas junto dos codigos nescessarios para rotaciona-lo (...)

# Manuseio da Raspberry

Para acessar a Raspberry será nescessario um cabo HDMI e um monitor disponivel, esses passos ja devem ser o suficiente para voce acessar sua Raspberry. Porém acho que rapidamente percebeu que a
interface dessa Rasp é um pouco diferente do que outras placas, isso por que nossa Raspberry usa o sistema operacional da Ubiquity Robotics que ja veio com algumas ferramentas, principalmente o ROS
Kinect para nós utilizarmos. A senha root do sistema operacional por padrão é "ubuntu"
Nota: pode ser que o teclado pareça um pouco estranho, mas isso ocorre pos o sistema operacional esta no padrão de teclado em ingles.

Voce tambem pode rapidamente perceber que não é dos mais otimizados, para facilita-lo, voce pode fazer uma conexão SSH com outro computador, basta utilizar o comando 

```
ssh ubiquityrobot@10.21.61.65
```
Caso apresente um erro, tente primeiramente verificar novamente o IP da Raspberry, use o seguinte comando no terminal da Raspberry para verificar
```
hostname -I
```
Caso ainda apresente erro, tente por usar o IP dado neste seguinte comando
```
ssh -X -C ubuntu@
```
(...)

# ROS
(...)


(...)
