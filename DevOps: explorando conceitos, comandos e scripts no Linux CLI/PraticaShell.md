A compreensão de práticas de scripting no shell possibilita que sejamos capazes de criar fluxos de trabalho otimizados, implementando práticas de integração e entrega contínuas. Além disso, essa abordagem facilita a configuração e gerenciamento da infraestrutura como código. Dessa forma, o aprofundamento dos estudos em Shell Scripting é um passo crucial no desenvolvimento como pessoa profissional em DevOps.

Sendo assim, criamos uma lista de atividades (não obrigatórias) para você praticar ainda mais todo o conteúdo que foi abordado ao longo dessa aula. Bora praticar a construção de scripts!?

Atividades

Elabore um script simples que exiba uma mensagem de boas-vindas quando executado.
Construa um script que seja capaz de criar uma cópia de segurança de um diretório específico.
Crie um script que solicite ao usuário o nome de um diretório e, em seguida, o crie.
Escreva um script que aceite um nome de arquivo como argumento e verifique se o arquivo existe.
Desenvolva um script que utilize um loop para contar de 1 a 5.
Caso necessite de ajuda para resolver as atividades, basta clicar na seção “Opinião da pessoa instrutora” para acessar instruções sobre como implementar as soluções.

Opinião do instrutor
•

Opções
Atividade 1


Copiar
#!/bin/bash
echo "Bem-vindo ao meu script!"
Utilizamos o comando echo para exibir a mensagem "Bem-vindo ao meu script!" no terminal quando o script é executado.

Atividade 2


Copiar
#!/bin/bash
tar -czf backup.tar.gz /caminho/do/diretorio
O script utiliza o comando tar para criar um arquivo compactado e tarball chamado "backup.tar.gz" do conteúdo do diretório especificado. O -czf indica a criação de um arquivo comprimido, usando gzip para compressão.

Atividade 3


Copiar
#!/bin/bash
echo "Digite o nome do diretório:"
read nome_diretorio
mkdir $nome_diretorio
Script interativo que solicita ao usuário o fornecimento de um nome de diretório. Na sequência, utiliza o comando mkdir para criação do diretório com o nome fornecido.

Atividade 4


Copiar
#!/bin/bash
echo "Digite o nome do arquivo:"
read nome_arquivo
if [ -e $nome_arquivo ]; then
  echo "O arquivo existe."
else
  echo "O arquivo não existe."
fi
Este script solicita ao usuário um nome de arquivo, em seguida, utiliza uma estrutura condicional (if) para verificar se o arquivo existe (-e). Dependendo do resultado, imprime uma mensagem indicando a existência ou não do arquivo.

Atividade 5


Copiar
#!/bin/bash
for i in {1..5}
do
  echo $i
done
O script utiliza um loop for para iterar de 1 a 5 e o comando echo para imprimir cada número no terminal.