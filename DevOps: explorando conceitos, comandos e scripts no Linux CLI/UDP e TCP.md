Segundo os cursos e conteúdos da Alura, tanto o TCP quanto o UDP são protocolos que operam na Camada de Transporte da rede. O objetivo de ambos é pegar os dados da aplicação e enviá-los de um ponto a outro. [1, 2] 
No entanto, a grande diferença está em como eles realizam esse transporte. [3] 
------------------------------
##  TCP (Transmission Control Protocol) [4] 
O TCP é o protocolo focado na confiabilidade. [5, 6, 7] 

* Orientado à Conexão: Antes de enviar qualquer dado, ele estabelece uma "sessão" (uma via de mão dupla) com o destino, garantindo que o receptor está pronto para ouvir. [2, 8] 
* Entrega Garantida e Ordenada: Ele numera todos os pacotes e verifica se houve perda ou corrupção de dados. Se algo se perder no caminho, ele exige o reenvio. Além disso, garante que os dados sejam montados exatamente na ordem em que foram enviados. [2, 5, 9, 10, 11] 
* Quando usar: É a escolha ideal quando a integridade da informação é fundamental. Exemplos: envio de e-mails, navegação web (HTTPS), transações financeiras e download de arquivos. [5, 8, 12] 

------------------------------
##  UDP (User Datagram Protocol) [2] 
O UDP é o protocolo focado na velocidade e eficiência. [7, 12] 

* Sem Conexão: Ele não perde tempo abrindo uma conexão ou verificando se o receptor está pronto; ele simplesmente envia os pacotes para o destino. [2, 6, 8, 13, 14] 
* Sem Garantia de Entrega: Não há confirmação de recebimento nem reenvio de pacotes perdidos. Se algum pacote se perder no meio do caminho, a aplicação simplesmente segue em frente e ignora a falha. [2, 8, 12] 
* Quando usar: É excelente para aplicações em tempo real, onde a fluidez é mais importante do que uma ou outra informação perdida. Exemplos: ligações de áudio/vídeo, streaming (lives e vídeos), jogos online e consultas de DNS. [5, 13, 15] 

------------------------------
##  Comparação Rápida

| Característica [2, 6, 7, 8, 9, 13] | TCP | UDP |
|---|---|---|
| Foco principal | Confiabilidade | Velocidade |
| Orientado à conexão? | Sim | Não |
| Verifica erros / reenvia? | Sim | Não |
| Velocidade | Mais lento (devido às verificações) | Muito rápido |
| Casos de uso | Web, banco, e-mail | Streaming, jogos, vídeo |

Se você quiser se aprofundar no assunto, recomendo ler o artigo da Alura sobre as [Diferenças entre TCP e UDP](https://www.alura.com.br/artigos/quais-as-diferencas-entre-o-tcp-e-o-udp) ou conferir os módulos de Redes e Protocolos da plataforma. [1, 5] 
------------------------------
Se estiver estudando para alguma prova ou projeto prático, me diga:

* Qual tipo de aplicação você está desenvolvendo ou analisando?
* Gostaria de entender como as portas de comunicação funcionam com esses protocolos?


[1] [https://www.alura.com.br](https://www.alura.com.br/conteudo/http-entendendo-web-por-baixo-dos-panos)
[2] [https://www.youtube.com](https://www.youtube.com/watch?v=H3p8rLOEbKk&vl=pt-BR)
[3] [https://cloud.ibm.com](https://cloud.ibm.com/docs/vpc?topic=vpc-understanding-icp&locale=pt-BR)
[4] [https://www.bosontreinamentos.com.br](https://www.bosontreinamentos.com.br/tag/protocolos/)
[5] [https://cursos.alura.com.br](https://cursos.alura.com.br/forum/topico-tcp-vs-udp-151479)
[6] [https://www.avast.com](https://www.avast.com/pt-br/c-tcp-vs-udp-difference)
[7] [https://cheapsslsecurity.com](https://translate.google.com/translate?u=https://cheapsslsecurity.com/blog/tcp-vs-udp-how-are-they-different/&hl=pt&sl=en&tl=pt&client=sge)
[8] [https://www.youtube.com](https://www.youtube.com/shorts/usfxUJG0wro)
[9] [https://cursos.alura.com.br](https://cursos.alura.com.br/forum/topico-duvida-quic-substitui-udp-ou-tcp-445943)
[10] [https://nordvpn.com](https://nordvpn.com/pt/blog/tcp-ou-udp/)
[11] [https://qnax.sh](https://qnax.sh/blog/tutoriais/o-que-e-o-protocolo-tcp-ip/)
[12] [https://www.estrategiaconcursos.com.br](https://www.estrategiaconcursos.com.br/blog/protocolo-tcp-udp/)
[13] [https://www.youtube.com](https://www.youtube.com/shorts/-BGxpQT6SHo)
[14] [https://www.tabnews.com.br](https://www.tabnews.com.br/racoelho/como-funciona-a-internet-parte-1-o-modelo-tcp-ip-a-fundacao-da-internet)
[15] [https://www.cloudflare.com](https://www.cloudflare.com/pt-br/learning/ddos/glossary/user-datagram-protocol-udp/)
