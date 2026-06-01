Vimos como utilizar o comando tar e como ele ajuda na compactação de arquivos. Isso é bastante útil quando precisamos movimentar arquivos entre diretórios e servidores, ou até mesmo mudar de infraestrutura ou plataforma. Dominar essa ferramenta é crucial, especialmente para realizar backups de dados críticos em nosso sistema.

Uma das coisas que mencionamos sobre a criação de scripts é a possibilidade de automação. Dessa forma, podemos realizar uma série de tarefas de forma mais autônoma, sem a necessidade de escrever comando a comando no terminal.

No script que desenvolvemos como teste, informamos o diretório dos arquivos que queríamos compactar para salvar os dados de backup de um sistema. Contudo, imagine que precisamos criar um script mais genérico, que permita informar diferentes diretórios para compactar arquivos, e um diretório específico para salvar.

Script para compactar arquivos
Como fazemos isso na prática? A pessoa usuária precisa informar no momento da execução do script quais arquivos deseja compactar e o nome do arquivo final.

A seguir, vamos abrir o nano, que é o nosso terminal de texto. A primeira coisa a fazer sempre é informar o interpretador desse script, com o comando #! /bin/bash.

Em seguida, a nossa lógica funcionará da seguinte forma: a pessoa usuária precisará informar alguns parâmetros. Pode informar o nome do arquivo final e o diretório em que deseja que esse arquivo seja salvo, além dos arquivos a serem compactados. Precisaremos de, pelo menos, dois parâmetros para o nosso script.

Para isso, podemos usar um comando bastante conhecido das linguagens de programação como Python e C, que é o if.

Nesse if, vamos testar o número de parâmetros passados pela pessoa usuária. Para isso, utilizaremos um cifrão e um jogo da velha ($#). Faremos uma contagem, e esse número precisa ser, pelo menos, igual a 2. Usaremos "-lt 2" para isso. Depois, fechamos o colchete.

Na sintaxe do if no Bash, colocamos um ponto e vírgula, seguido de um espaço, e então um then. Se essa condição for verdadeira, o que ele vai fazer? Primeiro, vai mostrar para a pessoa usuária usando um echo. Dentro desse echo, vai mostrar: "O programa, $0 requer nome do arquivo e arquivos a serem compactados"."

Agora, podemos iniciar uma nova linha. Vamos prestar atenção à indentação e dar uma saída de erro, exit 1. Agora, precisamos fechar esse bloco do if. Abrimos com o then, e para fechar, usamos um if ao contrário, que é o fi.


Copiar
if [ "$#" -lt 2 ]; then
    echo "O programa, $0 requer nome do arquivo e arquivos a serem compactados"
    exit 1
fi

A pessoa usuária passará alguns parâmetros. Como selecionamos esses parâmetros para executar o processo de compactação corretamente? O primeiro parâmetro será o nome do arquivo. Criaremos uma variável que receberá o primeiro parâmetro informado pela pessoa usuária, arquivo_saida.

Os demais parâmetros serão agrupados em uma variável que será um array, que agrupará todos os arquivos que serão compactados. Essa variável será passada para o nosso comando tar.

Vamos pegar do segundo parâmetro em diante. O primeiro é somente o nome do arquivo ou diretório que a pessoa usuária passará, onde esse arquivo será armazenado. Do segundo parâmetro em diante serão os arquivos a serem compactados.

Para fazer isso, vamos abrir os parênteses do array e aspas, cifrão, e agora vamos abrir chaves. O arroba iria pegar todos os parâmetros, mas não queremos pegar todos. O primeiro será usado como nome do arquivo. Então, todos os parâmetros a partir do segundo parâmetro.


Copiar
arquivo_saida="$1"
arquivos=("${@:2}")

Agora, falta fazer duas coisas. A primeira delas é compactar, realizar a ação desejada. Então, as opções são czf. Se você trocar uma dessas letras, o script pode funcionar de maneira inadequada ou apresentar até um erro que pode demorar um tempo para debugar.

Então, é czf e o primeiro parâmetro que passamos é o nome da variável de saída, arquivo_saida. E o segundo parâmetro são os arquivos a serem compactados, aquele array que criamos na variável arquivos. Então, vamos abrir chaves, arquivos e vamos colocar um arroba entre colchetes. Fechamos as chaves, fechamos as aspas.


Copiar
arquivo_saida="$1"
arquivos=("${@:2}")
tar -czf "$arquivo_saida" "${arquivos[@]}"

Vamos para a próxima linha, que será o echo "Compactado com sucesso em $arquivo_saida". Assim, ele informa o nome da variável de saída.

É muito importante prestar atenção ao nome das variáveis para que não tenhamos nenhum erro aqui no nosso script. Assim como nos espaços e na indentação.

Vamos dar um Ctrl + X agora para salvar o nosso arquivo. Vamos dar um Yes e o nome do nosso arquivo pode ser, por exemplo, compactador e pressionar a tecla Enter.

Se dermos um ls, o que vai ocorrer? Temos lá o compactador dentro do nosso diretório home. Mas observe que não salvamos com a extensão .sh. Podemos retornar ao nano compactador e agora podemos dar um Ctrl + X.

Note que dentro do diretório home, o compactador, o script que acabamos de criar, já está lá. O que podemos fazer é mudar a permissão de execução dele com o chmod. Vamos escrever chmod +x compactador.

Mudamos agora a permissão e podemos executá-lo diretamente no Bash. Então, vamos colocar o ./compactador. Observe que agora estamos executando só com um ponto e uma barra. Já que mudamos a permissão de execução desse arquivo. E não vamos passar parâmetro nenhum. Vamos dar um Enter para ver o que aparece para nós.

Aparece o seguinte: "O programa /compactador requer o nome do arquivo e os arquivos a serem compactados". Então, ele exibe uma mensagem de erro para a pessoa usuária. Isso já facilita bastante o uso desse script.

Agora, vamos testá-lo passando alguns parâmetros de fato. Vamos escrever ./compactador. O primeiro parâmetro será sempre o nome do arquivo de saída.

Vamos colocar, por exemplo, saida.tar.gz, que é a extensão final dele. E vamos informar dois arquivos que serão usados para compactar. Aqui, claro, precisaremos informar o caminho que esses arquivos se encontram no nosso sistema. Por isso, vou inserir /home/lucasrm/texto2.txt home/lucasrm/texto3.txt, usando esses dois arquivos em formato txt que estão dentro do diretório home mesmo, texto2.txt e texto3.txt.

Após pressionarmos o Enter, observe que não colocamos o caminho correto para o texto3. É só mudar com a seta de cima do mouse. Vamos dar uma barra. Inserimos uma barra antes do caminho para o texto3. Vamos dar um Enter.


Copiar
./compactador saida.tar.gz /home/lucasrm/texto2.txt /home/lucasrm/texto3.txt

Observe que ele removeu algumas barras dos endereços que colocamos. E deu Compactado com sucesso em saida.tar.gz. Vamos dar um ls no nosso diretório. Observe que está lá, saida.tar.gz.

Para verificar o que tem dentro dele, se de fato foi compactado corretamente, podemos usar o tar em uma função de descompactar: tar -tf. Vamos indicar saida.tar.gz e verificar. Estão lá os dois arquivos que passamos os parâmetros corretamente.

Então, nosso script funcionou. Conseguimos fazer a passagem de parâmetros. Agora, vamos explorar um pouco mais o uso dos scripts na automatização de tarefas em nosso sistema.


Para saber mais: passando parâmetros em scripts
Discutir no fórum
A passagem de parâmetros em scripts em Bash no Ubuntu é uma forma de fornecer informações ou argumentos para o script durante sua execução. Isso torna os scripts mais flexíveis e reutilizáveis, pois seu comportamento é ajustado de acordo com os argumentos fornecidos.

Essa passagem de parâmetros é realizada por meio de variáveis especiais, conhecidas como variáveis de posição. Elas são numeradas de 1 a 9, com $1 representando o primeiro argumento, $2 representando o segundo, e assim por diante. Além disso, todos os argumentos posicionais podem ser acessados através do $@.

A seguir, temos um exemplo de script que verifica se foram fornecidos exatamente dois argumentos na linha de comando. Se não, ele exibe uma mensagem de erro. Caso contrário, ele atribui os valores dos argumentos às variáveis arg1 e arg2 e os imprime.


Copiar
#!/bin/bash

if [ $# -ne 2 ]; then
  echo "Erro! Nao foram fornecidos dois argumentos"
  exit 1
fi

arg1=$1
arg2=$2

echo "O primeiro argumento é: $arg1"
echo "O segundo argumento é: $arg2"
