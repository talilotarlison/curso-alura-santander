Mãos na massa: conversão de arquivos
Discutir no fórum
Imagine que você tenha vários arquivos na extensão .jpg em um diretório do seu repositório local de armazenamento e deseja mudar sua extensão para .png. Seria possível criar um script que operasse essa conversão de forma prática e automatizada, ou seja, sem a necessidade de converter arquivo por arquivo?

Temos uma ferramenta muito útil nesse processo: o comando convert. Esse comando nos permite converter, editar e exibir imagens em diversos formatos.

A sintaxe do comando é bem prática:


Copiar
convert [opções] arquivo_entrada arquivo_saída

Para converter uma imagem de .jpg para .png, podemos escrever a seguinte instrução:


Copiar
convert imagem.jpg imagem.png

E se quiséssemos redimensionar um conjunto de imagens .jpg para uma resolução padrão 800x600?


Copiar
convert imagem.jpg -resize 800x600 imagem_redimensionada.jpg

Vamos praticar?
Crie um script que seja capaz de converter todos os arquivos com extensão .jpgde um diretório para .png de forma simples.

Não se esqueça de solicitar ao usuário o caminho do diretório em que as imagens estão armazenadas e exibir mensagens no terminal para indicar o sucesso ou falha no processo.

Opinião do instrutor
•

Opções
Um aspecto interessante de elaborar soluções baseadas em código são as diversas possibilidades de implementação. Vou compartilhar aqui o código que desenvolvi, explicando os principais aspectos de sua estrutura com alguns comentários:


Copiar
# Indicamos o interpretador
#!/bin/bash

# Solicitamos a indicação do caminho do diretório
read -p "Digite o caminho do diretório com as imagens JPG: " diretorio

# Verificamos se o diretório indicado existe
if [ ! -d "$diretorio" ]; then
    echo "Diretório não encontrado: $diretorio"
    exit 1
fi

# Convertemos todas as imagens JPG para PNG no diretório
for imagem_jpg in "$diretorio"/*.jpg; do
    convert "$imagem_jpg" "${imagem_jpg%.jpg}.png" && echo "Imagem convertida: ${imagem_jpg%.jpg}.png" || echo "Falha na conversão: $imagem_jpg"
done

echo "Conversão concluída!"
