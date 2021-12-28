# Criação de jogo de naves Bootcamp da MRV na DIO
## Descrição do projeto
O jogo consiste de um jogador (helicóptero à esquerda) que deve resgatar prisioneiros, e derrotar os inimigos (1 caminhão e o helicópetero à direita). O jogador tem 3 barras de vida.

Esse projeto utiliza o jQuery collision para retornar colisões entre dois seletores.


## Destaque
Como diferencial em relação ao visto no curso, implementou-se uma movimentação vertical do helicóptero inimigo. Conforme pode ser visto no bloco de código a seguir:
```javascript
function moveinimigo1() {
    posicaoX = parseInt($("#inimigo1").css("left"));
    $("#inimigo1").css("left", posicaoX - velocidade);

    if (posicaoY > 334) {
      posicaoY = 334;
      inimigo1Subindo = false;
      posicaoY -= Math.random(0, velocidade);
      $("#inimigo1").css("top", posicaoY);
    } else if (posicaoY < 0) {
      posicaoY = 0;
      inimigo1Subindo = true;
    }
    if (inimigo1Subindo) {
      posicaoY += Math.random(0, velocidade);
      $("#inimigo1").css("top", posicaoY);
    } else {
      posicaoY -= Math.random(0, velocidade);
      $("#inimigo1").css("top", posicaoY);
    }

    if (posicaoX <= 0) {
      posicaoY = parseInt(Math.random() * 334);
      $("#inimigo1").css("left", 694);
      $("#inimigo1").css("top", posicaoY);
    }
  } //Fim da função moveinimigo1()
```