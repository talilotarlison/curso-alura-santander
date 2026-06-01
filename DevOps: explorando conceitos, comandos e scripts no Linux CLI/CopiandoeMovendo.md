Mãos na massa: copiando e movendo arquivos entre diretórios
Discutir no fórum
Nesta aula vimos como podemos navegar entre diretórios além de copiar e mover arquivos nesses diretórios no Shell do CLI do Linux. Para realizar o que aprendemos você vai:

Criar dois diretórios chamados dir1 e dir2 na mesma posição hierárquica;
Entrar no diretório dir1 e criar dois arquivos chamados data1 e data2;
Copiar somente o conteúdo de dir1 para dir2;
Criar um novo diretório chamado dir3;
Mover o conteúdo de dir1 para dir3.
Vamos praticar?
Fizemos os passos acima durante a aula, agora é a sua vez de praticar o que aprendemos.

Opinião do instrutor
•

Opções
Para criar os dois diretórios usamos o comando:


Copiar
mkdir dir1 dir2
Podemos usar o comando ls para verificar se os dois diretórios foram criados corretamente.

Agora, entramos no diretório dir1 usando o seguinte comando:


Copiar
cd dir1
Para criar os dois arquivos data1 e data2 rodamos o comando a seguir:


Copiar
touch data1 data2
Com os arquivos criados, podemos sair de dir1 com o comando cd ...

Para copiar o conteúdo de dir1 para o diretório dir2, podemos rodar o seguinte comando.


Copiar
cp -r dir1/* dir2
Assim, os arquivos data1 e data2 que se encontram em dir1 serão copiados para dir2. É possível verificar se isso funcionou com o comando:


Copiar
ls ../dir2
Isso listará os arquivos que foram copiados para o diretórios.

Criamos um novo diretório dir3 com o comando e verificamos se ele foi criado corretamente:


Copiar
mkdir dir3
ls
Para mover o conteúdo de dir1 para dir3 usamos o comando:


Copiar
mv dir1/* dir3
Assim, todo o conteúdo que antes estava em dir1 foi movido para dir3. Podemos conferir isso rodando os comandos:


Copiar
ls ../dir1
Ao rodar o comando acima nenhum arquivo deverá ser listado.


Copiar
ls ../dir3
Ao rodar o comando acima os arquivos data1 e data2 serão listados.


Hora da prática
Discutir no fórum
A navegação eficiente em um servidor Linux é uma habilidade essencial para quem está iniciando no mundo DevOps. Possibilita a compreensão e manipulação de configurações do sistema, instalação de pacotes, análise de logs e implementação de scripts automatizados. Dessa forma, é fundamental que sejam praticadas atividades que propiciem o desenvolvimento dessa habilidade.

Pensando nisso, preparamos uma lista de atividades (não obrigatórias) para que você possa explorar ainda mais a navegação no servidor Linux. Bora praticar!?

Atividades

Crie um diretório chamado "Docs".
Abra o editor de texto Nano para editar um arquivo chamado "notas.txt".
Crie um arquivo vazio chamado "novo.txt".
Escreva "Olá, Mundo!" em um arquivo chamado "saudacao.txt".
Visualize o conteúdo do arquivo "saudacao.txt".
Adicione "Bem-vindo ao Linux!" ao final do arquivo "saudacao.txt".
Visualize o conteúdo do diretório “Docs”.
Se precisar de ajuda para resolver as atividades, clique na seção “Opinião da pessoa instrutora” e acesse instruções para implementação das soluções.

Opinião do instrutor
•

Opções
Atividade 1

mkdir Docs

Utilizamos o comando mkdir para criar um novo diretório. Aqui, estamos criando o diretório Docs no diretório atual.

Atividade 2

O comando nano abre o editor de texto Nano, permitindo a edição do arquivo "notas.txt". Se o arquivo não existir, o Nano o criará.

nano notas.txt

Atividade 3

Usamos o comando touchpara criar um novo arquivo vazio.

touch novo.txt

Atividade 4

O comando echo exibe a string especificada e o operador > redireciona a saída para o arquivo "saudacao.txt", criando-o se ainda não existir.

echo "Olá, Mundo!" > saudacao.txt

Atividade 5

O comando cat exibe o conteúdo de um arquivo no terminal.

cat saudacao.txt

Neste caso, será exibido o conteúdo do arquivo "saudacao.txt".

Atividade 6

O operador >> é usado para adicionar (anexar) texto ao final de um arquivo existente.

echo "Bem-vindo ao Linux!" >> saudacao.txt

Atividade 7

O comando ls é utilizado para listar o conteúdo de um diretório.

ls Docs


Você mencionou a manipulação de arquivos, que é um ponto central da aula. No Shell CLI do Linux, aprendemos a realizar diversas operações importantes para gerenciar o sistema de arquivos.

Além de manipular, a aula abordou como navegar entre diretórios e arquivos. Isso é fundamental para conseguir encontrar e acessar as informações que estão armazenadas no sistema. Vimos comandos que nos permitem listar o conteúdo de um diretório, entrar em subdiretórios e voltar para diretórios anteriores, o que facilita muito a localização de arquivos específicos.

Também exploramos como mover, copiar e remover arquivos, o que é essencial para manter os diretórios organizados. Essas ações são muito úteis para reorganizar seus dados, fazer backups ou limpar arquivos desnecessários. Outro ponto importante foi a criação de arquivos diretamente pelo Shell CLI, uma habilidade que simplifica a manutenção de dispositivos, como servidores, permitindo que você crie rapidamente arquivos de configuração ou de texto.

Dominar essas operações no Shell CLI é muito útil para gerenciar sistemas de forma eficiente e rápida. Continue estudando e praticando!