# ola pessoal!!
esse é um repositório pra criar juntos o jogo PONG
em Javascript.
o autor do proyeto original e https://medium.com/@willyan.dantunes?source=post_page-----554d8a97a68d--------------------------------

Conhecendo o jogo
Antes começarmos é preciso saber oque é o Pong. Pong é um dos primeiros jogo criados, ele simula um jogo de tênis de mesa e pode ser jogado por 2 jogadores. Cada jogador tem uma especie de barra que ele ponde controlar para cima ou para baixo com o intuito de rebater a bola, se bola passar da barra o jogador que rebateu ganha um ponto. É um jogo bem simples e perfeito para programadores iniciantes

Começando
Para começarmos vamos criar uma pasta onde ficará nossos arquivos. Dentro dessa pasta crie o arquivo index.html que será responsável por criar o elemento canvas que irá renderizar o jogo.

Com o canvas criado e com sua altura e largura definidas precisamos chamar o script que irá fazer o jogo funcionar, para isso vamos criar um arquivo com o nome de pong.js e chamá-lo no index.html

Agora será necessário configurar o arquivo javascript para ler o canvas e desenhar dentro dele. Para isso criaremos:

2 funções: setup() que será responsável por inicializar todas as variáveis e inicializar a função loop() que calcula onde a bola irá, se algum jogador marcou um ponto e no final redesenha o canvas com as novas alterações.

Algumas variáveis globais que são: ctx (canvas context responsável por renderizar objetos no canvas), p1_y (posição y do player 1), p2_y (posição y do player 2), p1_points e p2_points.

E algumas constantes como: h (height do canvas), w (width do canvas), pw (player width, como os dois jogadores tem o mesmo tamanho apenas uma constante é necessária), p_h ( o mesmo o player width vale para o player height), p1_x (posição x do player 1) e p2_x (posição x do player 2)

Inicializando a bolinha
Depois disso é preciso fazer uma função chamada initBall() que é responsável por resetar as variáveis que controlam a bolinha. Como essas variáveis vão ser resetadas em diversas partes do código é preciso colocar ela em uma função diferente.

A função para definir a bolinha precisa de algumas variáveis como: ball_y_orientation e ball_x_orientation (1 para direita e -1 para esquerda), ball_x (posição x da bolinha) e ball_y (posição y da bolinha)

Não se esqueça de chamar a função initBall() na função setup().

Desenhando as barras e controlando os players
Para isso iremos colocar os passos para desenhar um retângulo dentro de uma função. Essa função irá se chamar drawRect()

Como o jogo roda a 60 fps a função loop é responsável por fazer os cálculos e redesenhar o canvas a cada frame, para isso criaremos a função draw() que é responsável por desenhar todos os objetos do jogo mas por agora ela vai desenhar: o fundo, a barra divisória, os players e a bolinha

Depois dessa função é necessário chamar a função draw()na função loop()

O próximo passo é adicionar um listener para poder controlar as barras do players. Para isso criaremos um document.eventListener()que escuta dispara uma função se certo evento acontecer

E dentro da função loop()adicionaremos um trecho que código que é responsável por mover as barras

Agora as barras podem se mover

Codando ricochete da bolinha
Para começarmos precisamos deixar 2 coisas claras.

1ª — Quando a bolinha acerta o teto ou o chão ela apenas muda a orientação do eixo Y (se estava indo para cima agora e vai para baixo e vice-versa)

2ª — Quando a bolinha acerta a barra ela apenas muda a direção no eixo X (se estava indo para direita agora vai para esquerda)

Verificando se algum player pontuou, reiniciando jogo e exibindo os pontos
Nesse momento o jogo está quase pronto mas se você jogar irá ver que quando alguém marca um ponto o jogo não reseta e os pontos não são contabilizados. Então para começar vamos ver se algum player pontuou.

Para isso é necessário verificar se a bola no eixo X é menor que 0 ou seja se ela encostou e/ou passou da borda(ponto para o player 2) ou se ela é já encostou e/ou passou da outra borda para isso é necessário somar o tamanho da bola mais a posição dela e verificar se ela é maior que o height do canvas (ponto para o player 1).

Feito isso é só adicionar os pontos e resetar o game com a função initBall() que já está pronta

Para finalizarmos resta colocar os pontos no canvas e para isso usaremos uma função chamada writePoints() que é responsável por escrever os pontos no canvas

Com a função pronta basta apenas adicioná-la na função draw()


