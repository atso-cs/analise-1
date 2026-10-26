# Bolzano, Weierstrass e pontos fixos — 3.23 e 3.25–3.27

Sessão de **26 de outubro de 2026**.

[Índice](../README.md) · [Progresso](../PROGRESSO.md) · [Revisão curta](revisao-limites-e-continuidade.md)

Fonte: [ficha de exercícios](../materiais/Ficha_exercicios.pdf), páginas numeradas 8–9, correspondentes às páginas físicas 10–11 do PDF. O 3.24 não foi discutido nesta sessão e não fica considerado resolvido.

## 1. 3.23: zeros de um polinómio

O polinómio do enunciado é:

```math
f(x)=x^n+a_{n-1}x^{n-1}+\cdots+a_1x+a_0,
\qquad n\geq1.
```

Os coeficientes são reais e o coeficiente do termo de maior grau é 1. A função é contínua em todo o seu domínio, que é $\mathbb R$.

### O termo de maior grau determina o comportamento no infinito

Para $x\ne0$, colocamos $x^n$ em evidência:

```math
f(x)=x^n\left(
1+\frac{a_{n-1}}x+\cdots+
\frac{a_1}{x^{n-1}}+\frac{a_0}{x^n}
\right).
```

A escrita com reticências representa os termos existentes no polinómio; para $n=1$, a expressão é simplesmente $x(1+a_0/x)$. Nos dois infinitos, o fator entre parênteses tende a 1 e fica positivo para valores suficientemente grandes de $|x|$.

Não se transforma a identidade acima em $f(x)=x^n\cdot1$ para cada $x$. O fator **tende** a 1, o que permite determinar os limites.

### a) Grau ímpar: pelo menos uma raiz

Se $n$ é ímpar:

```math
\lim_{x\to-\infty}f(x)=-\infty,
\qquad
\lim_{x\to+\infty}f(x)=+\infty.
```

Estes limites garantem que podemos escolher números reais finitos $a<b$ tais que $f(a)<0<f(b)$. Não precisamos de encontrar valores explícitos para $a$ e $b$.

Como $f$ é contínua em $[a,b]$ e $f(a)f(b)<0$, pelo corolário de Bolzano existe $c\in(a,b)$ tal que $f(c)=0$.

> Logo, o polinómio tem pelo menos uma raiz real.

Bolzano é aplicado num intervalo com extremos reais, e não num suposto intervalo fechado com extremos infinitos.

### b) Grau par e um valor negativo: pelo menos duas raízes

Agora $n$ é par e o enunciado dá um ponto $x_0$ tal que $f(x_0)<0$. Temos:

```math
\lim_{x\to-\infty}f(x)
=\lim_{x\to+\infty}f(x)=+\infty.
```

Podemos escolher um ponto de cada lado de $x_0$:

```math
b<x_0<a,
\qquad f(b)>0,\quad f(x_0)<0,\quad f(a)>0.
```

Pela continuidade e pela mudança de sinal, Bolzano garante:

```math
\exists c_1\in(x_0,a):f(c_1)=0,
\qquad
\exists c_2\in(b,x_0):f(c_2)=0.
```

Como $c_2<x_0<c_1$, as raízes são distintas. Aplicar o teorema apenas em $[x_0,a]$ demonstra uma raiz; é a segunda aplicação, do outro lado, que completa o pedido.

> Logo, $f$ tem pelo menos duas raízes reais distintas.

## 2. 3.25: uma função por ramos e as hipóteses dos teoremas

```math
g(x)=
\begin{cases}
-x^2+2x,&x\leq2,\\
x,&x>2.
\end{cases}
```

### a) Valores pedidos

```math
g(0)=0,\qquad g(3)=3.
```

É a condição do ramo que decide qual expressão usamos.

### b) Interpretar e decidir uma proposição de existência

```math
\exists c\in(0,3):g(c)=\frac32.
```

A afirmação pergunta se existe pelo menos uma entrada entre 0 e 3 cuja saída seja $3/2$. Para a decidir, resolvemos a equação respeitando a região de cada ramo.

Para $0<x\leq2$:

```math
-x^2+2x=\frac32
\iff -x^2+2x-\frac32=0
\iff x^2-2x+\frac32=0.
```

O discriminante é:

```math
\Delta=(-2)^2-4\cdot1\cdot\frac32=-2<0.
```

Não há soluções reais neste ramo. Ao passar $3/2$ para o primeiro membro, o sinal fica negativo antes de multiplicar a equação inteira por $-1$.

Para $2<x<3$, a equação seria $x=3/2$. Mas $3/2$ não pertence a essa região, pelo que também não há solução neste ramo.

> A proposição é falsa: não existe $c\in(0,3)$ tal que $g(c)=3/2$.

Ao construir uma função auxiliar como $g(x)-3/2$, mudamos a função cujos valores estamos a calcular. Os valores da função original continuam a ser $g(0)=0$ e $g(3)=3$.

### c) Por que não se contradiz Bolzano

Na junção:

```math
\lim_{x\to2^-}g(x)=0=g(2),
\qquad
\lim_{x\to2^+}g(x)=2.
```

A função não é contínua em 2 e, portanto, não é contínua em $[0,3]$. Falha a hipótese de continuidade que permitiria garantir todos os valores intermédios entre $g(0)$ e $g(3)$.

> O resultado não contraria Bolzano, porque a função não satisfaz as hipóteses do teorema no intervalo considerado.

Não poder aplicar Bolzano, por si só, não prova que uma raiz ou um valor intermédio não exista. Aqui, a inexistência foi demonstrada pelas contas da alínea (b).

### d) Restrição a um intervalo: Weierstrass

Restringir $g$ a $[0,2]$ significa considerar apenas entradas nesse intervalo. Aí, usamos sempre a expressão $-x^2+2x$.

> Em $[0,2]$, a restrição de $g$ é contínua, por ser dada por uma expressão polinomial. Como $[0,2]$ é fechado e limitado, pelo teorema de Weierstrass essa restrição atinge um máximo e um mínimo.

Esta justificação já responde ao pedido de existência. Não é necessário calcular os valores dos extremos.

A descontinuidade da função completa em 2 não impede este argumento: a continuidade da restrição no extremo 2 é verificada a partir do interior de $[0,2]$, pela esquerda.

O aluno também fatorizou:

```math
g(x)=x(2-x).
```

Para $0<x<2$, ambos os fatores são positivos, logo $g(x)>0$. Como $g(0)=g(2)=0$, esta observação demonstra adicionalmente que o mínimo em $[0,2]$ é 0, atingido em dois pontos. A positividade, isoladamente, não é a razão que garante a existência do máximo.

### Valor de um extremo e ponto onde é atingido

O valor máximo de uma função num conjunto, quando existe, é único; pode ser atingido em vários pontos. O mesmo vale para o mínimo. «Existe pelo menos um ponto de máximo e pelo menos um ponto de mínimo» é uma formulação correta de existência; não se deve tratar o uso de «pelo menos» como erro.

Também é correto escrever simplesmente «a função atinge um máximo e um mínimo». Isto não afirma unicidade dos pontos onde os atinge.

Conhecer apenas os valores nos extremos do intervalo não localiza necessariamente o máximo ou o mínimo. Se uma função for crescente em $[a,b]$, o mínimo é $f(a)$ e o máximo é $f(b)$, mas os **valores** não têm de ser $a$ e $b$.

## 3. Domínio, conjunto de chegada e imagem

Esta distinção foi necessária nos exercícios 3.26 e 3.27:

```math
f:A\longrightarrow B.
```

- O domínio declarado é exatamente $A$: a função está definida em todos os seus elementos.
- Cada saída pertence a $B$; a seta não obriga a atingir todos os elementos de $B$.
- A imagem efetiva é $f(A)=\{f(x):x\in A\}$ e satisfaz $f(A)\subseteq B$.
- A igualdade $f(A)=B$ exige que todos os elementos de $B$ sejam atingidos. Essa condição é a sobrejetividade relativamente a $B$.

A ficha usa «contradomínio» para pedir a imagem em alguns exercícios anteriores. A distinção matemática relevante aqui é entre a notação com seta, que permite uma imagem menor, e a igualdade explícita para $f(A)$.

## 4. 3.26: pontos fixos

Um ponto fixo é uma entrada $c$ para a qual a saída é o próprio número:

```math
f(c)=c.
```

Não é a igualdade genérica $f(x)=f(c)$ que caracteriza um ponto fixo.

### a) Uma função contínua de [a,b] em [a,b]

Suponhamos $f:[a,b]\to[a,b]$ contínua. Para transformar a procura de um ponto fixo na procura de um zero, definimos:

```math
h(x)=f(x)-x.
```

A função $h$ é contínua, por ser diferença de duas funções contínuas. A condição sobre as saídas dá:

```math
a\leq f(x)\leq b\quad(x\in[a,b]).
```

Em particular:

```math
h(a)=f(a)-a\geq0,
\qquad
h(b)=f(b)-b\leq0.
```

Não precisamos de supor que $f$ é crescente. Os sinais resultam de as saídas ficarem no intervalo indicado.

Se $h(a)=0$ ou $h(b)=0$, já temos $f(a)=a$ ou $f(b)=b$, respetivamente. Basta um deles; não se conclui que os dois sejam pontos fixos.

Se nenhum desses valores for zero, então $h(a)>0$ e $h(b)<0$. Pelo corolário de Bolzano:

```math
\exists c\in(a,b):h(c)=0,
\qquad\text{isto é, }f(c)=c.
```

> Em qualquer dos casos, existe $c\in[a,b]$ tal que $f(c)=c$.

Se o intervalo se reduzir a um ponto ($a=b$), a própria condição $f:[a,a]\to[a,a]$ dá imediatamente $f(a)=a$.

### b) Um exemplo em [0,1) sem pontos fixos

O pedido é uma função contínua $f:[0,1)\to[0,1)$ sem ponto fixo. Escolhemos a média entre a entrada $x$ e o extremo excluído 1:

```math
f(x)=\frac{x+1}{2},\qquad x\in[0,1).
```

É uma função afim, logo contínua. Para cada entrada permitida:

```math
0\leq x<1
\quad\Longrightarrow\quad
\frac12\leq f(x)<1.
```

Assim, as imagens ficam no conjunto de chegada. A imagem efetiva é $[1/2,1)$: não precisa de conter zero nem de preencher todo $[0,1)$.

Finalmente:

```math
f(x)=x
\iff \frac{x+1}{2}=x
\iff x=1.
```

Como 1 não pertence ao domínio, não há ponto fixo. Podemos também observar que $x<(x+1)/2<1$ para todas as entradas do domínio.

As tentativas com constantes ajudam a perceber as condições:

- $f(x)=1$ não serve porque a saída 1 está fora de $[0,1)$.
- Uma constante $k\in[0,1)$ tem o ponto fixo $x=k$.
- $f(x)=x-1$ e $f(x)=x+1$ têm saídas fora do intervalo exigido.

Outros exemplos apresentados foram $(x+2)/3$ e $(x+3)/4$, definidos em $[0,1)$. Ambos são contínuos, têm imagens contidas em $[0,1)$ e a equação de ponto fixo só dá $x=1$.

## 5. 3.27: verdadeiro ou falso

| Alínea | Valor lógico | Ideia que decide |
| --- | --- | --- |
| a | Falsa | Uma função contínua em [0,1] atinge extremos; a imagem proposta (0,1) não os tem. |
| b | Verdadeira | Composição com a função contínua valor absoluto. |
| c | Verdadeira | Os dois ramos cobrem, em conjunto, todos os valores entre 0 e 6. |
| d | Falsa | A existência do limite do módulo não garante o limite da função. |
| e | Falsa | A continuidade do módulo não garante a continuidade da função. |

### a) A imagem de uma função contínua no intervalo fechado

A afirmação é: existe uma função contínua $f:[0,1]\to\mathbb R$ tal que $f([0,1])=(0,1)$.

Por Weierstrass, a função teria de atingir um máximo e um mínimo. Mas $(0,1)$ não tem máximo nem mínimo. Por exemplo, qualquer candidato $M<1$ dentro desse intervalo é ultrapassado por $(M+1)/2$, que também pertence ao intervalo; 1 não pode ser o máximo, pois não está incluído.

> A afirmação é falsa: a imagem indicada é incompatível com a existência de extremos atingidos.

O domínio $[0,1]$ não obriga, por si só, a que os valores mínimo e máximo sejam 0 e 1. No exemplo discutido $f(x)=1{,}3+0{,}5x$, o mínimo é $f(0)=1{,}3$ e o máximo é $f(1)=1{,}8$. Os pontos onde se atingem os extremos são entradas; os valores dos extremos são saídas.

É a condição adicional $f([0,1])=(0,1)$ que cria a contradição com Weierstrass.

### b) O módulo de uma função contínua

Se $f:\mathbb R\to\mathbb R$ é contínua, a função $x\mapsto|f(x)|$ é contínua por ser a composição de $f$ com $t\mapsto|t|$, que é contínua em $\mathbb R$. Não é necessário separar casos de sinal para repetir uma prova já conhecida sobre o módulo.

O texto da ficha contém uma omissão após «contínua em» nesta alínea; a afirmação foi interpretada na sessão como a propriedade da composição com o valor absoluto, válida em cada ponto de continuidade de $f$.

### c) Intervalos corretos dos ramos

```math
g:[0,4]\to\mathbb R,\qquad
g(x)=
\begin{cases}
x^2,&0\leq x<2,\\
x+2,&2\leq x\leq4.
\end{cases}
```

O ponto 2 pertence ao **segundo** ramo. A transcrição inicial do assistente trocou a inclusão desse ponto; o aluno assinalou a troca, confirmada na ficha. A expressão e os intervalos acima são os corretos.

Temos $g(0)=0$ e $g(4)=6$. A frase «toma todos os valores entre $g(0)$ e $g(4)$» refere-se aos valores entre 0 e 6, não a todos os reais.

As imagens dos ramos são:

```math
g([0,2))=[0,4),
\qquad
g([2,4])=[4,6].
```

Logo:

```math
g([0,4])=[0,4)\cup[4,6]=[0,6].
```

A afirmação é verdadeira. Também se pode justificá-la pelo teorema dos valores intermédios: os ramos são contínuos e, na junção, os dois laterais e $g(2)$ valem 4.

Entradas como $-6$ estão fora do domínio desta função e não podem ser usadas para refutar a afirmação.

### d) e e): um mesmo contraexemplo

Definimos deliberadamente a função:

```math
h(x)=
\begin{cases}
-1,&x<0,\\
1,&x\geq0.
\end{cases}
```

Os valores $-1$ e 1 vêm desta **definição**, não de uma regra universal sobre funções. A condição do ramo compara a entrada $x$ com zero.

Aplicar o módulo significa aplicar o valor absoluto à saída:

```math
|h(x)|=
\begin{cases}
|-1|=1,&x<0,\\
|1|=1,&x\geq0.
\end{cases}
```

Assim, $h$ não é constante, mas $|h|$ é a função constante 1. Uma função constante também é uma função. Neste exemplo, $h(0)=1$ e $|h(0)|=1$.

Para a alínea (d):

```math
\lim_{x\to0}|h(x)|=1,
\qquad
\lim_{x\to0^-}h(x)=-1,\quad
\lim_{x\to0^+}h(x)=1.
```

O limite do módulo existe e o da função não existe. A afirmação é falsa.

Para a alínea (e), $|h|$ é contínua em todo $\mathbb R$, mas $h$ é descontínua em zero. A afirmação também é falsa.

### Não confundir |h(x)| com |x|

Na primeira expressão, aplica-se o módulo à **saída de h**. Na segunda, aplica-se diretamente à entrada $x$. A função $x\mapsto|x|$ é contínua em zero:

```math
\lim_{x\to0^-}|x|=\lim_{x\to0^-}(-x)=0,
\qquad
\lim_{x\to0^+}|x|=0=|0|.
```

O «bico» do gráfico não é uma descontinuidade.

## 6. Estado do estudo

As resoluções foram construídas a partir das tentativas e dúvidas da sessão. A interpretação de imagem, a prova do ponto fixo e o contraexemplo com módulo exigiram ajuda e permanecem temas a consolidar. A leitura da resolução não é registada como execução autónoma.

O aluno corrigiu a inclusão de 2 em 3.27(c) e questionou corretamente a necessidade de substituir a formulação «pelo menos um» em Weierstrass. O [progresso](../PROGRESSO.md) distingue estas evidências das explicações apenas apresentadas.
