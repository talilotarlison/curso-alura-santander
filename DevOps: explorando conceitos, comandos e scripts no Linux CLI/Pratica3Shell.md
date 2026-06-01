Hora da prática
Discutir no fórum
O monitoramento de processos e o agendamento de tarefas em servidores são práticas essenciais para garantir a eficiência, disponibilidade e segurança dos sistemas e aplicações. O agendamento de tarefas automatiza processos recorrentes por meio do cron jobs, permitindo a execução automática de scripts, backups, atualizações e outras operações.

Criamos uma lista de atividades (não obrigatórias) para que você possa praticar ainda mais sobre como monitorar processos e agendar tarefas em um servidor. Bora avançar nos estudos de forma prática!?

Atividades

Crie um script que utiliza comandos como ps e grep para monitorar os processos que estão utilizando uma porcentagem significativa da CPU.
Desenvolva um script que utiliza comandos como ps e sort para exibir os processos que estão consumindo mais memória.
Crie um script que verifica se um processo específico está em execução e exibe seu status.
Elabore um script para analisar os logs do sistema em busca de mensagens de erro relacionadas a processos.
Crie um script para monitorar as mensagens de erro no log do sistema em intervalos regulares usando cron jobs. O script deve registrar em um arquivo as últimas 5 linhas de mensagens de erro, possibilitando uma visão periódica da atividade do sistema.
Caso necessite de ajuda para resolver as atividades, basta clicar na seção “Opinião da pessoa instrutora” para acessar instruções sobre como implementar as soluções.

Opinião do instrutor
•

Opções
Atividade 1


Copiar
#!/bin/bash
echo "Top 5 processos por uso de CPU:"
ps aux --sort=-%cpu | head -n 6
O script utiliza o comando ps para listar todos os processos em execução, ordena-os pelo uso de CPU em ordem decrescente e exibe as seis primeiras linhas, mostrando os cinco principais processos e o cabeçalho.

Atividade 2


Copiar
#!/bin/bash
echo "Top 5 processos por uso de memória:"
ps aux --sort=-%mem | head -n 6
O script é bastante similar ao elaborado na atividade, no entanto agora ordena os processos pelo uso de memória.

Atividade 3


Copiar
#!/bin/bash
processo="nginx"
if pgrep $processo > /dev/null; then
  echo "$processo está em execução."
else
  echo "$processo não está em execução."
fi
O script utiliza o comando pgrep para verificar se o processo "nginx" está em execução, exibindo uma mensagem apropriada.

Atividade 4


Copiar
#!/bin/bash
echo "Últimas 10 linhas de mensagens de erro:"
tail -n 10 /var/log/syslog | grep "error"
O script mostra as últimas 10 linhas do log do sistema relacionadas a mensagens de erro.

Atividade 5

Script


Copiar
#!/bin/bash
echo "Mensagens de erro - $(date)" >> /caminho/do/log_monitorado.txt
tail -n 5 /var/log/syslog | grep "error" >> /caminho/do/log_monitorado.txt
Configuração do cron:


Copiar
# Adicione a seguinte linha ao crontab para executar o script a cada duas horas
0 */2 * * * /caminho/do/seu/script.sh
O script adiciona as últimas 5 linhas de mensagens de erro ao arquivo de log especificado e é configurado para ser executado a cada duas horas usando cron.


O que aprendemos?
Discutir no fórum
Nessa aula, você aprendeu a:
Verificar o status dos processos em execução no servidor para monitorar o seu desempenho.
Utilizar operadores e comandos para filtrar e coletar dados a partir de textos.
Construir scripts para monitorar o estado operacional de sistemas como servidores web.
Executar scripts usando o crontab para implementar um cronograma de execução automática no sistema.