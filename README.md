# Flexbox em CSS

## Introdução ao Flex Box
Foi projetado como um modelo de layout unidimensional e como um método que pode oferecer distribuição de espaço entre itens em uma interface e recursos de alinhamento.

### Flex Container
É a tag que envolve os itens, será nela que iremos aplicar a propriedade "display: flex". Transforma todos os seus itens filhos em flex itens.
Como está ilustrado na imagem: 

<img width="300" src="/img/8.png"/>

Vale resaltar que essa propriedade de display/ essa inicialização de container pode ser feita em qualquer tipo de tag, seja ela uma div, um spam, h1, h2, ou até mesmo um link (a), a partir do momento que essa tag possui itens filhos, ela é passivel de ser aplicada a propriedade "display-flex".

**Propriedades relacionadas:**
- display: inicializador do container
- flex-direction: faz o direcionamento dos itens, seja em linha ou em coluna
- flex-wrap: vai ser aplicado para quebra de linha ou não 
- flex-flow: é uma abreviação para a definição do direction e wrap
- justify-content: alinha os itens do container de acordo com a sua direção 
- align-items: alinha os itens de acordo com o eixo do container
- align-content: alinha as linhas do container

### Flex Item
São os elementos filhos diretos do Flex Container. E também podem se tornar Flex Container.

**Propriedades relacionadas:**
- flex-grow: define o fator de crescimento
- flax-basis: define o tamanho inicial do item antes da distribuição do espaço restante dentro do container
- flex-shrink: define a capacidade de redução
- flex: é uma abreviação para definir o flex-grow, flex-basis e flex-shrink
- order: define a ordem de distribução e listagem dos itens 
- align-self: define o alinhamento de um item especifico do container

## Fundamentos do Flex Box

### Display: flex
Torna a tag um elemento do tipo flex container, e assim automaticamente todos os seus filhos diretos desta tag, tornam-se em flex items.

- Os flex items acupam todo o espaço da sua div(da sua caixa):

<img width="300" src="/img/1.jpg"/>


- A aplicação do display-flex faz com que os items do container pai(onde foi aplicado o display-flex) ele passa a ocupar o maximo do seu conteúdo e se abrigando dentro desse container, respeitando a orientação em linha:

<img width="300" src="/img/3.jpg"/>

_Obs.:_ 
- Antes da aplicação do display-flex, foi aplicado na div pai algumas propriedades para facilitar essa visualização, propriedades de max-width, border solid e padding:

<img width="300" src="/img/2.jpg"/>

### Flex-direction
É a propriedade que estabelece o eixo principal do container, definindo assim a direção que os flex items são colocados no flex container.

**Eixos**:

- **row (padrão):** à direção do texto, esquerda para direita.

- **row-reverse:** sentido oposto à direção do texto. Modo leitura.

<img width="300" src="/img/6.jpg"/>

> Por padrão a div sem nenhuma propriedade aplicada, alinha seus elementos em linha/horizontal. 
<img width="280" src="/img/5.jpg"/>

- **column:** ordenação de cima para baixo, em coluna unica.

- **column-reverse:** ordenação inversa, de baixo para cima.

<img width="300" src="/img/7.jpg"/>

### Flex-wrap
É a propriedade que define se os itens devem ou não quebrar a
linha. 
Por padrão eles não quebram linhas, isso faz com que os flex itens sejam compactados além do limite do conteúdo.

- **nowrap (padrão)**, não permite a quebra de linha.

<img width="300" src="/img/9.jpg"/>

- **wrap:** permite a quebra de linha assim que um dos flex itens não puder mais ser compactado.

<img width="300" src="/img/10.jpg"/>

- **wrap-reverse:** permite a quebra de linha assim que um dos flex itens não puder mais ser compactado, porém na direção contrária da linha, acima.
