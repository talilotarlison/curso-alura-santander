Hora da prática
Discutir no fórum
A automatização de tarefas por meio de Shell Scripting promove a consistência e a reprodutibilidade, aspectos essenciais para ambientes de desenvolvimento e operações ágeis. Ao criar scripts para tarefas rotineiras e complexas, as pessoas profissionais de DevOps garantem que as implementações, configurações e manutenções de sistemas sejam executadas de maneira padronizada, minimizando variações entre ambientes.

Para que você possa explorar ainda mais como implementar scripts no contexto da automatização de tarefas, preparamos uma lista de atividades práticas (não obrigatórias).

Atividades

Elabore um script que automatiza a atualização de pacotes do sistema operacional.
Crie um script que renomeie todos os arquivos em um diretório, adicionando um prefixo ou sufixo especificado.
Desenvolva um script que automatiza a criação de usuários no sistema, solicitando ao usuário que forneça o nome e outros detalhes necessários.
Construa um script para monitorar o espaço em disco usando o comando df na coleta de informações.
Escreva um script para automatizar o backup de um diretório específico para um local de destino, utilizando a compressão gzip.
Caso necessite de ajuda para resolver as atividades, basta clicar na seção “Opinião da pessoa instrutora” para acessar instruções sobre como implementar as soluções.

Opinião do instrutor
•

Opções
Atividade 1


Copiar
#!/bin/bash
sudo apt update -y
sudo apt upgrade -y
O script utiliza os comandos apt update e apt upgrade para automatizar a atualização de pacotes no sistema operacional Debian/Ubuntu. O parâmetro -y é usado para confirmar automaticamente todas as perguntas de confirmação.

Atividade 2


Copiar
#!/bin/bash
prefixo="Novo_"
for arquivo in *; do
  mv "$arquivo" "$prefixo$arquivo"
done
O script adiciona o prefixo "Novo_" aos nomes de todos os arquivos no diretório em que é executado.

Atividade 3


Copiar
#!/bin/bash
echo "Digite o nome do novo usuário:"
read nome_usuario
sudo useradd -m $nome_usuario
sudo passwd $nome_usuario
O script solicita ao usuário o nome do novo usuário, cria um diretório pessoal para o usuário (useradd -m), e define uma senha (passwd).

Atividade 4


Copiar
#!/bin/bash
limite=90
espaco=$(df -h | awk 'NR==2 {print $5}' | sed 's/%//')

if [ $espaco -gt $limite ]; then
  echo "Alerta: Espaço em disco excedeu $limite%."
else
  echo "Espaço em disco está abaixo do limite."
fi
O script coleta a porcentagem de espaço em disco usando o comando df, compara com um limite predefinido (90% neste exemplo) e emite um alerta se exceder.

Atividade 5


Copiar
#!/bin/bash
origem="/caminho/do/diretorio"
destino="/caminho/do/backup"
data=$(date +"%Y%m%d")
tar -czf $destino/backup_$data.tar.gz $origem
O script utiliza o comando tar para criar um arquivo compactado e tarball, adicionando a data ao nome do arquivo para distinguir backups diários. O gzip (-z) é usado para compressão.