WSL como alternativa ao uso do VirtualBox
Discutir no fórum
Alguns computadores podem apresentar certa lentidão e até mesmo alguns bugs quando usamos máquinas virtuais (VMs) através de softwares de virtualização como o VirtualBox.

Se este for o seu caso, temos uma alternativa de virtualização de ambiente Linux no Windows que pode facilitar bastante sua trajetória de aprendizado aqui no curso: o uso do Windows Subsystem for Linux (WSL). O WSL é um recurso do Windows 10 e Windows 11 que permite executar um ambiente Linux diretamente no Windows, sem a necessidade de uma VM. Com o WSL, você pode instalar distribuições Linux (como Ubuntu, Debian, e outras) e utilizá-las como se fossem aplicativos nativos do Windows.

Todos os passos e configurações que faremos aqui são compatíveis com o WSL, sendo assim você não terá nenhuma perda de aprendizado ao optar por esse ambiente.

Para começar a usar o WSL, siga os passos abaixo:

Abra o PowerShell como administrador e execute o comando wsl --install.

Após a instalação inicial, você pode instalar outras distribuições disponíveis na Microsoft Store. Assim, basta escolher a distribuição Ubuntu (a mesma que estamos usando no curso).

Para acessar o WSL, basta procurar pela distribuição instalada no menu iniciar (pesquise, por exemplo, "Ubuntu"). Com alguns poucos passos, você terá um terminal Linux pronto para dar sequência aqui no curso! 

https://www.alura.com.br/artigos/wsl-executar-programas-comandos-linux-no-windows

Temos um artigo que você pode consultar caso tenha alguma dúvida em relação ao processo de configuração e funcionamento do WSL.


Nessa aula, você aprendeu:
Que um sistema operacional exerce o papel de gerenciar a utilização dos recursos de um hardware.
Que há diferentes distribuições do Linux para selecionar a opção mais adequada em um determinado caso de uso.
Como instalar um sistema operacional em uma máquina virtual para realização de testes e estudos.
Como utilizar o protocolo SSH para acessar servidores remotamente.