# Flexbox em CSS

## Introdução ao Flex Box
Foi projetado como um modelo de layout unidimensional e como um método que pode oferecer distribuição de espaço entre itens em uma interface e recursos de alinhamento.

### Flex Container
É a tag que envolve os itens, será nela que iremos aplicar a propriedade _"display: flex"_. Transforma todos os seus itens filhos em flex itens.
Como está ilustrado na imagem: 

<img width="400" src="/img/8.png"/>

Vale resaltar que essa propriedade de display/essa inicialização de container pode ser feita em qualquer tipo de tag, seja ela uma div, um spam, h1, h2, ou até mesmo um link (a), a partir do momento que essa tag possui itens filhos, ela é passivel de ser aplicada a propriedade _"display:flex"_.

**Propriedades relacionadas:**

- **display:** inicializador do container;
- **flex-direction:** faz o direcionamento dos itens, seja em linha ou em coluna;
- **flex-wrap:** vai ser aplicado para quebra de linha ou não; 
- **flex-flow:** é uma abreviação para a definição do direction e wrap;
- **justify-content:** alinha os itens do container de acordo com a sua direção; 
- **align-items:** alinha os itens de acordo com o eixo do container;
- **align-content:** alinha as linhas do container.

### Flex Item
São os elementos filhos diretos do Flex Container. E também podem se tornar Flex Container.

**Propriedades relacionadas:**

- **flex-grow:** define o fator de crescimento;
- **flax-basis:** define o tamanho inicial do item antes da distribuição do espaço restante dentro do container;
- **flex-shrink:** define a capacidade de redução;
- **flex:** é uma abreviação para definir o flex-grow, flex-basis e flex-shrink;
- order: define a ordem de distribução e listagem dos itens; 
- **align-self:** define o alinhamento de um item especifico do container.

## Fundamentos do Flex Box 
### Propriedades relacionadas ao Flex Container
<img width="400" src="/img/13.png"/>

#### Display: flex
Torna a tag um elemento do tipo flex container, e assim automaticamente todos os seus filhos diretos desta tag, tornam-se em flex items.

``` CSS
.container {
  display: flex; /* or inline-flex */
}
```

- Os flex items acupam todo o espaço da sua div(da sua caixa):

<img width="400" src="/img/1.jpg"/>

- A aplicação do _display:flex_ faz com que os items do container pai(onde foi aplicado o display:flex) ele passa a ocupar o maximo do seu conteúdo e se abrigando dentro desse container, respeitando a orientação em linha:

<img width="400" src="/img/3.jpg"/>

_Obs.:_ 
- Antes da aplicação do display:flex, foi aplicado na div pai algumas propriedades para facilitar essa visualização, propriedades de max-width, border solid e padding:

<img width="400" src="/img/2.jpg"/>

#### Flex-direction
É a propriedade que estabelece o eixo principal do container, definindo assim a direção que os flex items são colocados no flex container.

``` CSS
.flex-container {
  flex-direction: row | row-reverse | column | column-reverse;
}
```

**Eixos:**

- **row (padrão):** à direção do texto, esquerda para direita;

- **row-reverse:** sentido oposto à direção do texto. Modo leitura;

<img width="400" src="/img/6.jpg"/>

> Por padrão a div sem nenhuma propriedade aplicada, alinha seus elementos em linha/horizontal. 
<img width="400" src="/img/5.jpg"/>

- **column:** ordenação de cima para baixo, em coluna unica;

- **column-reverse:** ordenação inversa, de baixo para cima.

<img width="400" src="/img/7.jpg"/>

#### Flex-wrap
É a propriedade que define se os itens devem ou não quebrar a
linha. 
Por padrão eles não quebram linhas, isso faz com que os flex itens sejam compactados além do limite do conteúdo.

``` CSS
.flex-container {
  flex-wrap: nowrap | wrap | wrap-reverse;
}
```

- **nowrap (padrão)**, não permite a quebra de linha;

<img width="400" src="/img/9.jpg"/>

- **wrap:** permite a quebra de linha assim que um dos flex itens não puder mais ser compactado;

<img width="400" src="/img/10.jpg"/>

- **wrap-reverse:** permite a quebra de linha assim que um dos flex itens não puder mais ser compactado, porém na direção contrária da linha, acima.

#### Flex-flow
É um atalho para as propriedades **flex-direction** e **flex-wrap**.
Porém _seu uso não é tão comum_, visto que, quando mudamos o flex-direction para column, mantemos o padrão do flex-wrap que é nowrap.

``` CSS
.flex-container {
  flex-flow: row nowrap | row wrap | column nowrap | column wrap;
}
```

#### Justify-Content
Essa propriedade vai se encarregar de alinhar os itens dentro do container de acordo com a direção pretendida e tratar da distribuição de espaçamento entre eles.

_Obs:_ caso seus itens esteja ocupando 100% de todo o container, ela não se aplica.

``` CSS
.flex-container {
  justify-content: flex-start | flex-end | center | space-between | space-around | space-evenly;
}
```

**Variações:**
- **flex-start:** faz o alinhamento no início do container;
- **flex-end:** posiciona todos os itens de acordo com a sobra de espaço no final do container(respeitando o limite do conteúdo que os itens ocupam);
- **center:** posiciona todos os elementos ao centro do container;
- **space-between:** cria um espaçamento igual entre os elementos. Ele pega o primeiro elemento, coloca muito próximo ao início do container(próximo a borda essquerda) e o último elemento coloca bem próximo ao final do container(próximo a borda direita);
- **space-around:** os espaçamentos do meio são duas vezes maiores que o inicial e final.

<img width="400" src="/img/17.png"/>

#### Align-items
Trata do alinhamento dos flex itens de acordo com o eixo do container.
O alinhamento é diferente para quando os itens estão em colunas(vertical) ou linhas(horizontal).
Permite o alinhamento central no eixo vertical(no meio da tela).
A direferença entre o justify-content é que ele não vai precisar necessiariamente ter conhecimento da altura dos itens filhos do container.

``` CSS
.flex-container {
  align-items: stretch | flex-start | flex-end | center | baseline;
}
```

**Tipos de alinhamento:**
- **flex-start:** alinhamento dos itens no início;
- **flex-end:** alinhamento dos itens no final;
- **center:** alinhamento dos itens ao centro;
- **stretch:** padrão, e os flex itens crescem igualmente;
- **baseline:** alinhamento de acordo com a linha base da tipografia dos itens.

<img width="400" src="/img/14.png"/>

#### Align-content
É a propriedade responsável por tratar o alinhamento das linhas do container em relação ao eixo vertical do container.

Precisamos que:
- O container utilize quebra de linhas (flex-wrap: wrap);
- A altura do container seja maior que a soma das linhas dos itens.

``` CSS
.flex-container {
  align-content: flex-start | flex-end | center | space-between | space-around | stretch;
}
```

**Tipos de alinhamento:**
- **flex-start:** alinhamento dos itens no início;
- **flex-end:** alinhamento dos itens no final;
- **center:** alinhamento dos itens ao centro;
- **space-between:** cria um espaçamento igual entre os elementos;
- **space-around:** os espaçamentos do meio são duas vezes
maiores que o inicial e final;
- **stretch:** é o padrão e os flex itens crescem igualmente

<img width="400" src="/img/17.png"/>

### Propriedades relacionadas aos Flex Items

<img width="400" src="/img/12.png"/>

#### Flex-grow
Define a proporcionalidade de crescimentos dos itens, respeitando o tamanho de seus conteúdos internos.

_Obs:_ _justify-content não irá funcionar_ caso tenhamos adicionado ao nosso flex container.

<img width="400" src="/img/18.png"/>

``` CSS
.flex-item {
  flex-grow: <numero>; /* o valor default(padrão) é 0 */
}
```

#### Flex-basis
É a propriedade que estabelece o tamanho inicial do item antes das distribuição de espaço restante dentro dele, usando como base o conteúdo interno disposto.

``` CSS
.flex-item {
  flex-basis: auto /* default */
          or <width>
}
```

**Valores possíveis:**
- **auto:** caso o item não tenha tamanho, este será proporcional ao conteúdo do item;
- **px, %, em, ...:** são valores exatos previamente definidos;
- **0 (zero):** terá relação com a definição do flex-grow.
