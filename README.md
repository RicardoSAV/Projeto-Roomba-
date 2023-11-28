# Plataforma de robótica móvel para aplicação em pesquisa: Projeto-Roomba.

Bem Vindo(a) ao repositório do projeto "Desenvolvimento de uma plataforma para aplicação em pesquisa na área de robótica autônoma móvel". A plataforma de pesquisa visa a incorporação de projetos por parte de colaboradores do campus, o que faz com que seja substancial ofertar de maneira clara as instruções de utilização do robô. Dessa maneira, o presente repositório busca orientar quaisquer utilizadores sobre tudo o que é pertinente ao uso da plataforma.

# O projeto:

O Projeto-Roomba, como apelidado pelos autores, é composto por um robô aspirador de pó da fabricante iRobot, equipado com uma Raspberry Pi e um Arduino. A presença desses componentes facilita projetos de pesquisa relacionados à área de robótica móvel, pois permite um manuseio manual das funções do robô. Informações mais detalhadas estão presentes no documento completo do artigo em anexo. [Anexar PDF do artigo quando finalizado]

# Visualização manual dos códigos no Arduino

Com muito cuidado, conecte o Arduino a um computador via um cabo USB A/B, e em seguida, acesse o Arduino IDE. O arquivo "Create Test", que pode ser encontrado neste repositório, deve conter um código que foi usado no Arduino durante o desenvolvimento da plataforma. É altamente recomendável o uso do mesmo como base para a inicial compreensão da interface do Roomba. Este arquivo contém configurações de inicialização do robô nos modos corretos, bem como movimentação das rodas, conforme o manual iRobot® Create® 2 Open Interface (OI) anexo ao repositório. [Anexar PDF do manual]

# Manuseio da Raspberry Pi

Para acessar manualmente o sistema operacional da Raspberry, será necessário conectar um cabo HDMI em um monitor disponível e na placa. Para interagir com o sistema também é possível conectar um mouse e teclado nas entradas USB presentes na mesma. O sistema operacional instalado na Raspberry se trata de uma distribuição do Ubiquity Robotics baseado em Ubuntu 16.04, que possui algumas ferramentas à disposição. A senha do sistema é, por padrão, “ubuntu”. É importante mencionar que o input do teclado é incompatível ao modelo Abnt-2, sendo possível adequar o sistema a esse modelo através do terminal, pela inserção da seguinte linha de comando:

```
setxkbmap -model abnt2 -layout br
```

 A Raspberry Pi não possui uma grande otimização, podendo funcionar de forma mais lenta que um computador comum, por exemplo. Dessa forma, é possível estabelecer uma comunicação SSH (Secure Shell), em que há a possibilidade de envio de comandos em um terminal de outro computador compatível diretamente para a Raspberry. Para isso, basta inserir o seguinte comando no computador externo:
```
ssh ubiquityrobot@10.21.61.65
```

Caso apresente um erro, tente primeiramente verificar se o IP da Raspberry é compatível com o código anterior. Digite a seguinte linha de comando no terminal da Raspberry:
```
hostname -I
```
Caso o IP gerado seja diferente, tente utilizar o primeiro código novamente com o novo IP. Se ainda apresentar um erro, tente usar o IP no seguinte comando:
```
ssh -X -C ubuntu@
```

# Pinagens

A pinagem se trata da posição de todos os pinos nos circuitos das placas ou das entradas seriais. A imagem a seguir demonstra a pinagem da entrada serial do Roomba, que se trata de um conector mini-DIN de 7 pinos.

[inserir essa imagem da forma correta no repositório]
Os pinos relevantes para o projeto são os 3, 4 e 6 (ou 7). É importante destacar que o cabo equivalente ao RX (Receiver) deve ser conectado, no Roomba, ao TX (Transmitter), enquanto o cabo equivalente ao TX deve ser conectado ao RX.
Para identificar qual cabo é qual, observe os pinos em que estão conectados no Arduino, conforme a pinagem do mesmo, demonstrada na imagem a seguir:

[inserir essa imagem da forma correta no repositório]


A pinagem da Raspberry Pi Modelo B é demonstrada na imagem a seguir:

[inserir essa imagem da forma correta no repositório]
	


