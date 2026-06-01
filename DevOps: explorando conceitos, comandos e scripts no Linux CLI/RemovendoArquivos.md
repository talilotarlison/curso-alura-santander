Removendo arquivos e diretórios
Discutir no fórum
No Linux, a remoção de arquivos e diretórios pode ser feita de forma simples utilizando comandos no terminal como rm para arquivos e rmdir ou rm -r para diretórios. No entanto, é importante ter cautela ao utilizar opções como -f e -r, pois a remoção é definitiva e não há uma lixeira para recuperação posterior.

Para remover um arquivo, use o comando rm (remove):


Copiar
rm nome_do_arquivo

Para remover um diretório vazio, use o comando rmdir:


Copiar
rmdir pasta_vazia

Remover um diretório com conteúdo Para remover um diretório e todos os seus arquivos e subdiretórios, use o comando rm com a opção -r (recursivo):


Copiar
rm -r nome_do_diretorio
