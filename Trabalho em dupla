# Introduçao à Computação Gráfica

*Este documento trata de expor os trabalhos referentes a disciplina de ICG ministrada na Universidade Federal da Paraíba* 

Neste primeiro momento foi pedido a implementação de três funções: PutPixel, DrawLine e DrawTriangle que servem respectivamente para desenhar pontos, linhas e triângulos na tela do computador.

# Rasterização

Rasterizar nada mais é do que desenhar imagens na tela do computador, porém, essa representação é feita através de pixels que são pequenos
pontos pintados na tela, usando o padrão de cor: vermelho, verde, azul e alpha.Abaixo segue uma demonstração de como ficaria
a rasterização de uma reta:

![rasterizacao](https://user-images.githubusercontent.com/40369696/44006271-ffdad556-9e57-11e8-910e-b691df793951.PNG)


# PutPixel

Função que pinta na tela um pixel dado a posição x,y e as cores, segue o código:

![putpixel2](https://user-images.githubusercontent.com/40369696/44057217-d235a8d2-9f20-11e8-8901-b149bafdd5f0.PNG)


É possível observar que as posições são multiplicadas por 4,isso se da porque cada pixel ocupa 4 posições na memória referentes a cada cor,alem disso para que se possa locomover a posição y de forma adequada, faz-se necessário o uso da largura da tela criada, que no caso esta em 512x512.Resultado da aplicação dessa função quando chamada 6 vezes com cores e posições diferentes:

![put_pixel](https://user-images.githubusercontent.com/40369696/44006476-8945ec56-9e5b-11e8-9bdb-14415655dbb5.PNG)


#DrawLine

Função que desenha uma linha na tela recebendo como parâmetro o ponto inicial e o ponto final.Para implementar essa função é necessário usar algum algorítmo de rasterização,no caso foi utilizado o de bresenham:

![bresenham](https://user-images.githubusercontent.com/40369696/44007604-1e9b4b9e-9e6f-11e8-945f-306d2caf18e1.PNG)

É calculado a variação do x e y final em relaçao ao inicial,depois o ponto de decisão e os incrementos.Então inicia-se um loop para pintar os pixels de acordo com a variável de decisão,resultado dessa função implementada:

![bresehan_1_oc](https://user-images.githubusercontent.com/40369696/44007672-0da78d74-9e70-11e8-9770-695702d6a0a2.PNG)

Porém, esse algoritmo não funciona para todos os octantes,sendo necessário generaliza-lo:

![octates](https://user-images.githubusercontent.com/40369696/44007730-e0a942ee-9e70-11e8-897f-5ca62ea0a526.PNG)

Observa-se que a generalização é feita a partir da observação do delta x e do delta y em relação a 0,após algumas modficações no algoritmo em relação ao que foi dito, chega-se ao seguinte resultado(Função DrawLine chamada 8 vezes para representar os octantes):

![bresehan_gene](https://user-images.githubusercontent.com/40369696/44007775-9e39a574-9e71-11e8-9a9a-29416b6c8569.PNG)

Mas foi especificado para ter interpolação entre cores quando o DrawLine fosse chamado,entao foi feito mais incrementos na função para se chegar a interpolação,foi usado a fórmula da distância entre dois pontos:

![pontos](https://user-images.githubusercontent.com/40369696/44007821-3f56791e-9e72-11e8-8262-e76917fbf3a1.PNG)

Depois foi feito cáculos envolvendo as 2 cores passadas como parâmetro,subtraindo-as depois dividindo pelo delta x ou delta y, o resultado disso é guardado em variáveis que vão incrementando outra variável que começará com as cores do ponto inicial:

![bresehan_gene_inter](https://user-images.githubusercontent.com/40369696/44007881-e0db75c8-9e72-11e8-85a9-83123d2ab64a.PNG)

![cubo](https://user-images.githubusercontent.com/40369696/44008001-7fd07f42-9e74-11e8-8082-a417a5d78948.PNG)

# Função DrawTriangle

A função DrawTriangle se responsabiliza por rasterizar um triângulo na tela usando as funções ja implementadas anteriormente,ou seja se resume a chamar a DrawLine 3 vezes:

![triangulo](https://user-images.githubusercontent.com/40369696/44008044-02a4edb8-9e75-11e8-8b84-12c1846d19ff.PNG)

![mix](https://user-images.githubusercontent.com/40369696/44008066-4411af20-9e75-11e8-81f5-188fdf7fe8b9.PNG)

# Resultados

As três funções foram implementadas da maneira pedida e se mostraram efiazes no resultado final.

Principais dificuldades: Um pequeno intervalo de tempo foi gasto para conseguir rodar o framework no windows, pois ele vem pronto para linux,também mostrou-se trabalhoso fazer a interpolação de cores e generalizar o bresenham.

Possíveis melhorias: Otimização do código.

# Referências:

https://mundoeducacao.bol.uol.com.br/matematica/distancia-entre-dois-pontos.htm
https://en.wikipedia.org/wiki/Bresenham%27s_line_algorithm

https://pt.wikipedia.org/wiki/Rasteriza%C3%A7%C3%A3o

E também foi feito o uso de materiais disponibilizados pelo professor


*Contribuidores Danillo Medeiros e Renan Ribeiro
