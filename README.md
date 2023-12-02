# Plataforma de robótica móvel para aplicação em pesquisa: Projeto-Roomba.

Bem Vindo(a) ao repositório do projeto "Desenvolvimento de uma plataforma para aplicação em pesquisa na área de robótica autônoma móvel". A plataforma de pesquisa visa a incorporação de projetos por parte de colaboradores do campus, o que faz com que seja substancial ofertar de maneira clara as instruções de utilização do robô. Dessa maneira, o presente repositório busca orientar quaisquer utilizadores sobre tudo o que é pertinente ao uso da plataforma.

# O projeto:

O Projeto-Roomba, como apelidado pelos autores, é composto por um robô aspirador de pó da fabricante iRobot, equipado com uma Raspberry Pi e um Arduino. A presença desses componentes facilita projetos de pesquisa relacionados à área de robótica móvel, pois permite um manuseio manual das funções do robô. Informações mais detalhadas estão presentes no documento completo do artigo em anexo.

# Visualização manual dos códigos no Arduino

Com muito cuidado, conecte o Arduino a um computador via um cabo USB A/B, e em seguida, acesse o Arduino IDE. Os arquivos "Test", que podem ser encontrados neste repositório, devem conter códigos que foram usados no Arduino durante o desenvolvimento da plataforma. É altamente recomendável o uso dos mesmos como base para a inicial compreensão da interface do Roomba. Este arquivo contém configurações de inicialização do robô nos modos corretos, bem como movimentação das rodas, conforme o manual iRobot® Create® 2 Open Interface (OI) anexo ao repositório. ![Confira esse Manual para melhor compreensão dos códigos](https://github.com/RicardoSAV/Projeto-Roomba-/blob/main/create2-oi-spec.pdf)

O arquivo [code_main](/code_main) possui um controle basico de movimento comentado, é possível utilizá-lo como base para o desenvolvimento.

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

![Alt text](https://cdn.discordapp.com/attachments/747231290998390895/1179154847505854504/image.png?ex=6578c087&is=65664b87&hm=180db630c2902b602fe7cc2604503add7087202d0ba56744c35cb332dcd627c5&) 

Os pinos relevantes para o projeto são os 3, 4 e 6 (ou 7). É importante destacar que o cabo equivalente ao RX (Receiver) deve ser conectado, no Roomba, ao TX (Transmitter), enquanto o cabo equivalente ao TX deve ser conectado ao RX.
Para identificar qual cabo é qual, observe os pinos em que estão conectados no Arduino, conforme a pinagem do mesmo, demonstrada na imagem a seguir:

![Alt text](https://cdn.discordapp.com/attachments/747231290998390895/1179154962710798436/image.png?ex=6578c0a2&is=65664ba2&hm=1ed65c9448953fa77068470f671e33e293daa05db7fb9f1f063dfd28d3daa400&)


A pinagem da Raspberry Pi Modelo B é demonstrada na imagem a seguir:

![Alt text](https://cdn.discordapp.com/attachments/747231290998390895/1179155046370381834/image.png?ex=6578c0b6&is=65664bb6&hm=445088b53bd6a62f3458d9409ad57900ad4e00690695db94ab1aa1d1d97430bc&)

# Como estabelecer controle do Arduino e do robô através de um terminal

Os códigos de movimentação devem já estar gravados no Arduino. Para mais detalhes, verifique o arquivo em anexo que descreve o funcionamento dos códigos base. Primeiramente, certifique-se de que os cabos estejam devidamente conectados nos pinos corretos. Em seguida, abra um terminal por onde deseja controlar o Arduino. Digite o seguinte comando para verificar o nome do dispositivo:

```
ls /dev/tty*
```
Em seguida, utilize o seguinte código para iniciar a comunicação, colocando o /tty encontrado no código anterior:
```
sudo screen /dev/ttyUSB0 9600
```
Caso apresente um erro, tente instalar o screen através do seguinte comando:
```
sudo apt-get install screen
```
Com isso, o terminal deve ter iniciado o modo desejado. No código base, o input do teclado "0" para o movimento do robô. Enquanto o "1" faz com que o mesmo ande para a frente. Se tudo estiver correto, ao apertar a tecla 1 o robô deverá começar a andar após alguns segundos. Esse código pode ser customizado de acordo com as necessidades.

	


