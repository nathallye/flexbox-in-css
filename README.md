# Flexbox em CSS

## Introdução ao Flex Box
Foi projetado como um modelo de layout unidimensional e como um método que pode oferecer distribuição de espaço entre itens em uma interface e recursos de alinhamento.


### Flex Container
É a tag que envolve os itens, será nela que iremos aplicar a propriedade "display: flex". Transforma todos os seus itens filhos em flex itens.
Como está ilustrado na imagem: 
https://miro.medium.com/max/1400/1*bw4hK0MYxFXbw7ylW2fR5Q.png

Vale resaltar que essa propriedade de display/ essa inicialização de container pode ser feita em qualquer tipo de tag, seja ela uma div, um spam, h1, h2, ou até mesmo um link (a), a partir do momento que essa tag possui itens filhos, ela é passivel de ser aplicada a propriedade "display-flex".

> Propriedades relacionadas:
- display: inicializador do container
- flex-direction: faz o direcionamento dos itens, seja em linha ou em coluna
- flex-wrap: vai ser aplicado para quebra de linha ou não 
- flex-flow: é uma abreviação para a definição do direction e wrap
- justify-content: alinha os itens do container de acordo com a sua direção 
- align-items: alinha os itens de acordo com o eixo do container
- align-content: alinha as linhas do container


### Flex Item
São os elementos filhos diretos do Flex Container. E também podem se tornar Flex Container.

> Propriedades relacionadas:
- flex-grow: define o fator de crescimento
- flax-basis: define o tamanho inicial do item antes da distribuição do espaço restante dentro do container
- flex-shrink: define a capacidade de redução
- flex: é uma abreviação para definir o flex-grow, flex-basis e flex-shrink
- order: define a ordem de distribução e listagem dos itens 
- align-self: define o alinhamento de um item especifico do container
