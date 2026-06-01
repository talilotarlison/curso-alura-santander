Falamos muito sobre servidores até o momento, principalmente porque estamos lidando diretamente com um. Mas por que falamos tanto sobre servidor?

Quando acessamos uma página web, como a página da Alura, para realizar este ou outros cursos, esta página não está hospedada no seu celular ou no seu computador, mas em um servidor.

Normalmente, desejamos ter um acesso rápido, ágil, não queremos esperar alguns segundos para o vídeo carregar. Isso afeta muito a nossa experiência como pessoas usuárias de um site ou mesmo de um serviço, como, por exemplo, um serviço de streaming.

Para que isso ocorra de forma ágil e com qualidade, precisamos de um software rodando no nosso servidor, especificamente para atender a essas solicitações encaminhadas pelos nossos dispositivos para ele. Este software é chamado de servidor web.

A finalidade deste servidor é atender às solicitações que chamamos de HTTP, protocolo de comunicação usado para interagir com recursos e acessar páginas web localizadas em servidores.

Mas como preparamos um servidor web? É possível instalarmos um servidor web neste servidor Ubuntu no qual temos trabalhado? Sim, é possível!

Instalando um servidor web
Para isso, temos algumas opções, inclusive open source (código aberto). Por exemplo, o Apache e o Nginx são bastante utilizados e são opções open source.

O Nginx é bastante usado quando temos requisitos de performance e trabalhamos com conteúdos estáticos. Por outro lado, o Apache funciona bem quando precisamos atender uma demanda grande e vamos utilizar uma grande variedade de funcionalidades e módulos no projeto.

Vamos instalar, por exemplo, o Nginx no nosso servidor para testar?

Instalando o Nginx
Precisamos, inicialmente, fazer uma atualização dos pacotes instalados no servidor. Para isso, usamos primeiro o comando sudo apt update no terminal, e depois o sudo apt-get update.


Copiar
sudo apt update


Copiar
sudo apt-get update

Após a atualização, para instalar o Nginx, usamos o comando sudo apt install seguido de nginx.


Copiar
sudo apt install nginx

Uma vez finalizada a instalação, vamos verificar se o nosso servidor web está rodando no servidor Ubuntu. Para isso, temos uma ferramenta que nos possibilita monitorar o desempenho de unidades e serviços dentro do servidor: o systemctl.

Nesse caso, usamos o comando sudo systemctl status, porque queremos verificar o status do servidor que acabamos de instalar, o nginx.


Copiar
sudo systemctl status nginx

Poderíamos usar esse mesmo comando systemctl sem informar que queremos visualizar o status do nginx. Nesse caso, ele faria uma verificação de todos os serviços em todas as unidades.


Copiar
sudo systemctl status

Trata-se de uma ferramenta muito útil para diagnosticar erros e monitorar o desempenho das diferentes unidades de serviço instaladas no nosso servidor.

Conclusão
Agora que temos um servidor web instalado, que tal pensarmos um pouco em como seria, na prática, o monitoramento do funcionamento desse servidor web, do status dele? Como poderíamos verificar isso de forma automática para praticar um pouco a questão do monitoramento contínuo, tão importante no contexto DevOps?

Nginx, pois é especialmente eficiente com conteúdo estático e alta performance.

O Nginx é conhecido por sua alta eficiência e performance quando lidando com conteúdo estático e alto volume de tráfego, o que condiz com as necessidades do projeto em questão.