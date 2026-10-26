# Análise Matemática I — Prolongamentos, continuidade e Bolzano

Apontamentos atualizados em **25 de outubro de 2026**.

[Índice](../README.md) · [Progresso](../PROGRESSO.md) · [Continuidade e prolongamento: fundamentos](continuidade-e-prolongamento.md)

Fonte: [Ficha_exercicios.pdf](../materiais/Ficha_exercicios.pdf), páginas numeradas 7–8, correspondentes às páginas físicas 9–10 do PDF. Os enunciados foram conferidos no texto e na imagem da ficha. Estas notas registam as resoluções estudadas de 3.13–3.17 e 3.21–3.22; não incluem uma resolução do 3.23.

## 1. Prolongar por continuidade

Prolongar uma função a um ponto excluído do domínio significa acrescentar um valor nesse ponto, conservando os valores anteriores. Para que o prolongamento seja contínuo, o valor acrescentado tem de coincidir com o limite da função.

Se a origem pode ser aproximada pelos dois lados do domínio, procurar um prolongamento contínuo a zero equivale a procurar um número real $K$ tal que:

```math
\lim_{x\to0^-}f(x)
=\lim_{x\to0^+}f(x)
=K.
```

Se os dois laterais forem diferentes, ou se não existir um limite real e finito, nenhum valor real atribuído em zero resolve o problema. Se houver um limite real $L$, o valor que torna o prolongamento contínuo é necessariamente $K=L$.

«À origem» indica o ponto $x=0$; não obriga a escolher $K=0$.

## 2. 3.13(a): os laterais não coincidem

A função é a da alínea 3.12(e):

```math
f(x)=\frac1{1-e^{1/x}}.
```

A expressão exige $x\ne0$. Para um real $x\ne0$, o denominador não se anula: $e^{1/x}=1$ implicaria $1/x=0$, o que não acontece. Portanto, o domínio original é $\mathbb R\setminus\{0\}$.

### Pela direita

Se $x\to0^+$, então $1/x\to+\infty$ e $e^{1/x}\to+\infty$. O denominador $1-e^{1/x}$ tende a $-\infty$, pelo que:

```math
\lim_{x\to0^+}\frac1{1-e^{1/x}}=0.
```

Os valores da fração são negativos perto de zero pela direita, mas o valor do limite é $0$.

### Pela esquerda

Se $x\to0^-$, então $1/x\to-\infty$ e $e^{1/x}\to0$. Assim:

```math
\lim_{x\to0^-}\frac1{1-e^{1/x}}
=\frac1{1-0}=1.
```

Não se deve confundir $e^t\to0$ quando $t\to-\infty$ com uma tendência para valores negativos: a exponencial é sempre positiva.

**Conclusão para escrever:**

> Os limites laterais em zero são $1$ e $0$, logo o limite bilateral não existe. Assim, a função não admite prolongamento por continuidade à origem.

## 3. 3.13(b): cancelamento e domínio do prolongamento

```math
f(x)=\frac{x^4+x^2}{x^4+3x}.
```

Começamos pelo domínio da expressão original. O denominador fatoriza-se como:

```math
x^4+3x=x(x^3+3).
```

Logo:

```math
D_f=\mathbb R\setminus\{0,-\sqrt[3]{3}\}.
```

No domínio original, podemos fatorizar também o numerador e cancelar um fator $x$:

```math
\frac{x^4+x^2}{x^4+3x}
=\frac{x^2(x^2+1)}{x(x^3+3)}
=\frac{x(x^2+1)}{x^3+3},
\qquad x\ne0,\quad x\ne-\sqrt[3]{3}.
```

O cancelamento não altera o domínio da função original. O que ele permite é calcular o limite por uma expressão equivalente nos pontos próximos de zero:

```math
\lim_{x\to0}f(x)
=\lim_{x\to0}\frac{x(x^2+1)}{x^3+3}
=\frac{0(0^2+1)}{0^3+3}=0.
```

O denominador da expressão simplificada tende a $3\ne0$, por isso a substituição é válida. O prolongamento contínuo à origem é:

```math
F(x)=
\begin{cases}
\dfrac{x^4+x^2}{x^4+3x},&x\ne0,\quad x\ne-\sqrt[3]{3},\\
0,&x=0.
\end{cases}
```

O domínio passa a ser:

```math
D_F=D_f\cup\{0\}
=\mathbb R\setminus\{-\sqrt[3]{3}\}.
```

Também podemos escrever a função prolongada numa única expressão:

```math
F(x)=\frac{x(x^2+1)}{x^3+3},
\qquad x\ne-\sqrt[3]{3}.
```

Esta nova função está definida em zero e vale aí $0$. O ponto $-\sqrt[3]{3}$ continua excluído; acrescentar o valor em zero não elimina as restantes restrições.

**Conclusão para escrever:**

> Como $\lim_{x\to0}f(x)=0$, existe prolongamento contínuo à origem, obtido definindo $F(0)=0$. O domínio da função prolongada é $\mathbb R\setminus\{-\sqrt[3]{3}\}$.

## 4. 3.14: o máximo de duas funções contínuas num ponto

Sejam $f$ e $g$ contínuas em $a$. A função $h=\max(f,g)$ é o **máximo ponto a ponto**:

```math
h(x)=\max\{f(x),g(x)\}.
```

Para cada valor de entrada $x$, comparamos os dois números $f(x)$ e $g(x)$ e escolhemos o maior. Não estamos a procurar o maior valor global que uma das funções assume.

### De onde vem a identidade sugerida

Para quaisquer números reais $u$ e $v$:

```math
\max\{u,v\}=\frac{u+v+|u-v|}{2}.
```

Se $u\geq v$, temos $|u-v|=u-v$, e o lado direito dá $(u+v+u-v)/2=u$. Se $u<v$, temos $|u-v|=v-u$, e o resultado é $(u+v+v-u)/2=v$.

Aplicando a identidade aos números $u=f(x)$ e $v=g(x)$, obtemos:

```math
h(x)=\frac{f(x)+g(x)+|f(x)-g(x)|}{2}.
```

### Prova da continuidade em a

Como $f$ e $g$ são contínuas em $a$, os seus limites nesse ponto são $f(a)$ e $g(a)$. A soma, a diferença e a composição com o valor absoluto preservam a continuidade. Explicitamente:

```math
\begin{aligned}
\lim_{x\to a}h(x)
&=\frac{f(a)+g(a)+|f(a)-g(a)|}{2}\\
&=\max\{f(a),g(a)\}\\
&=h(a).
\end{aligned}
```

Não é necessário que $f(a)=g(a)$. A identidade funciona quer os valores coincidam, quer um seja maior do que o outro. Também não precisamos de calcular uma interseção dos gráficos.

**Conclusão para escrever:**

> Pela identidade do máximo e pela continuidade de $f$, $g$ e do valor absoluto, temos $\lim_{x\to a}\max\{f(x),g(x)\}=\max\{f(a),g(a)\}$. Logo, $\max(f,g)$ é contínua em $a$.

O enunciado só supõe continuidade de $f$ e $g$ em $a$. Assim, a conclusão justificada é a continuidade do máximo **nesse ponto**, sem presumir continuidade em todo $\mathbb R$.

## 5. 3.15: escolher o valor que preenche a junção

```math
f(x)=
\begin{cases}
\dfrac{\sqrt{2+x}-2}{x-2},&x\ne2,\\
m,&x=2.
\end{cases}
```

A raiz exige $x\geq-2$. O ramo especial define o valor em $2$, portanto o domínio da função completa é $[-2,+\infty)$, para qualquer valor real de $m$.

Para obter continuidade em $2$, procuramos o valor do limite do primeiro ramo e igualamo-lo a $f(2)=m$. A substituição inicial dá $0/0$. Usamos o conjugado para produzir o fator $x-2$:

```math
\frac{\sqrt{2+x}-2}{x-2}
=\frac{(2+x)-4}{(x-2)(\sqrt{2+x}+2)}
=\frac1{\sqrt{2+x}+2},
\qquad x\ne2.
```

Perto de $2$, o conjugado é positivo e o cancelamento é válido fora do ponto. Assim:

```math
\lim_{x\to2}f(x)
=\frac1{\sqrt4+2}
=\frac14.
```

**Conclusão para escrever:**

> A função é contínua em $2$ se e só se $m=\lim_{x\to2}f(x)=1/4$.

O valor escolhido não surge por substituição na expressão original em $2$, onde essa expressão não está definida; surge do seu comportamento nas proximidades.

## 6. 3.16: duas junções, duas equações

```math
f(x)=
\begin{cases}
x+1,&1<x<3,\\
x^2+ax+b,&|x-2|\geq1.
\end{cases}
```

A condição com valor absoluto significa estar a uma distância pelo menos $1$ de $2$:

```math
|x-2|\geq1
\quad\Longleftrightarrow\quad
x\leq1\text{ ou }x\geq3.
```

Os ramos cobrem todo $\mathbb R$. Cada expressão é polinomial, logo é contínua na região em que se aplica. Os únicos pontos a verificar são $1$ e $3$, onde a expressão muda.

### Junção em 1

O primeiro ramo não inclui $1$; o valor $f(1)$ vem do ramo quadrático. Temos:

```math
\lim_{x\to1^-}f(x)=f(1)=1+a+b,
\qquad
\lim_{x\to1^+}f(x)=2.
```

A continuidade exige $1+a+b=2$, ou seja, $a+b=1$.

### Junção em 3

De novo, o valor no ponto vem do ramo quadrático:

```math
\lim_{x\to3^-}f(x)=4,
\qquad
\lim_{x\to3^+}f(x)=f(3)=9+3a+b.
```

A continuidade exige $9+3a+b=4$, ou seja, $3a+b=-5$.

### Resolver as duas condições simultaneamente

```math
\begin{cases}
a+b=1,\\
3a+b=-5.
\end{cases}
```

Subtraindo a primeira equação à segunda, obtemos $2a=-6$, logo $a=-3$. Substituindo em $a+b=1$, resulta $b=4$.

**Conclusão para escrever:**

> As condições de continuidade nas junções dão $a=-3$ e $b=4$. Para esses valores, os laterais coincidem com $f(1)=2$ e $f(3)=4$. Como os ramos são contínuos nas restantes regiões, a função é contínua em todo $\mathbb R$.

## 7. 3.17: continuidade num intervalo fechado

```math
f(x)=
\begin{cases}
m,&x\leq0,\\
\dfrac{x^2-x}{x^2-4x+3},&0<x<1,\\
k,&x\geq1.
\end{cases}
```

O pedido é escolher $m$ e $k$ para obter continuidade em $[0,1]$. No interior $(0,1)$, a expressão racional já é contínua, pois os zeros do denominador são $1$ e $3$, que não pertencem a esse intervalo aberto.

Nos extremos do intervalo, verificamos a continuidade a partir do seu interior:

```math
\lim_{x\to0^+}f(x)=f(0)=m,
\qquad
\lim_{x\to1^-}f(x)=f(1)=k.
```

É por isso que surgem $0^+$ e $1^-$ neste exercício. Estamos a estudar a continuidade da função no intervalo fechado indicado.

Para $0<x<1$, fatorizamos:

```math
\frac{x^2-x}{x^2-4x+3}
=\frac{x(x-1)}{(x-1)(x-3)}
=\frac{x}{x-3}.
```

O cancelamento é válido nessa região porque $x\ne1$. Ele não muda os valores atribuídos pelos outros ramos nos extremos. Logo:

```math
\lim_{x\to0^+}f(x)=\frac0{0-3}=0,
\qquad
\lim_{x\to1^-}f(x)=\frac1{1-3}=-\frac12.
```

**Conclusão para escrever:**

> A função é contínua em $[0,1]$ se e só se $m=0$ e $k=-1/2$, pois estes valores fazem coincidir os limites tomados pelo interior do intervalo com os valores da função nos extremos.

A função completa tem domínio $\mathbb R$: o ramo racional só é usado em $(0,1)$, e os ramos constantes cobrem os restantes pontos. Não se exclui $3$ com base num denominador de um ramo que não é usado nesse ponto.

## 8. Teorema de Bolzano: provar a existência de uma raiz

Se uma função real $F$ é contínua em $[\alpha,\beta]$ e assume valores de sinais opostos nos extremos, então existe pelo menos um ponto interior onde vale zero:

```math
F(\alpha)F(\beta)<0
\quad\Longrightarrow\quad
\exists c\in(\alpha,\beta):F(c)=0.
```

A intuição é que uma função contínua, ao passar de um valor positivo para um negativo, tem de passar por zero. As hipóteses que justificam essa conclusão são a continuidade no intervalo inteiro e a mudança de sinal.

Para aplicar o teorema a uma equação, começamos por escrever todos os termos de um lado e chamamos $F$ à expressão resultante. Assim, resolver a equação passa a ser procurar zeros de $F$.

Uma prova por Bolzano deve indicar:

1. A função auxiliar e por que é contínua no intervalo escolhido.
2. Os valores, ou pelo menos os sinais, nos extremos.
3. O intervalo aberto onde o teorema garante uma raiz.

O teorema garante **pelo menos uma** raiz; não fornece o seu valor exato nem garante que seja a única.

## 9. 3.21: uma raiz entre zero e pi

O enunciado pede provar que a equação

```math
\sin^3x+\cos^3x=0
```

tem pelo menos uma raiz em $(0,\pi)$. Definimos:

```math
F(x)=\sin^3x+\cos^3x.
```

Esta função é contínua em $\mathbb R$, pelas operações entre funções contínuas; em particular, é contínua em $[0,\pi]$. Nos extremos:

```math
F(0)=0^3+1^3=1>0,
\qquad
F(\pi)=0^3+(-1)^3=-1<0.
```

**Conclusão para escrever:**

> Como $F$ é contínua em $[0,\pi]$ e $F(0)F(\pi)=-1<0$, o teorema de Bolzano garante a existência de $c\in(0,\pi)$ tal que $F(c)=0$. Logo, a equação tem pelo menos uma raiz nesse intervalo.

O aluno reconstruiu esta prova na conversa. A passagem relevante é ligar explicitamente a mudança de sinal e a continuidade à existência de uma raiz no intervalo pedido.

### Alternativa algébrica e cuidado ao dividir por cosseno

Também é possível determinar uma raiz. Antes de dividir por $\cos^3x$, precisamos de excluir os pontos onde o cosseno se anula. No intervalo $(0,\pi)$, isso só acontece em $\pi/2$, que não é solução porque:

```math
F(\pi/2)=1^3+0^3=1.
```

Para uma solução no intervalo pedido, podemos então dividir por $\cos^3x\ne0$:

```math
\sin^3x+\cos^3x=0
\quad\Longleftrightarrow\quad
\tan^3x+1=0
\quad\Longleftrightarrow\quad
\tan x=-1.
```

O valor $x=3\pi/4$ pertence a $(0,\pi)$ e verifica a equação. Encontrar esse valor confirma a existência por outro caminho; a prova por Bolzano já respondia ao pedido sem precisar de o calcular.

## 10. 3.22: duas raízes em intervalos separados

O enunciado confirmado na ficha é:

```math
x-\ln x=2.
```

Para transformar o pedido numa procura de zeros, definimos:

```math
F(x)=x-\ln x-2,
\qquad D_F=(0,+\infty).
```

A função é contínua no seu domínio. Para garantir **duas raízes distintas**, procuramos duas mudanças de sinal em intervalos abertos disjuntos. Não basta aplicar Bolzano duas vezes em intervalos que possam conter a mesma raiz.

### Escolher pontos com logaritmos conhecidos

O ponto $1$ é útil porque $\ln1=0$, dando um valor negativo:

```math
F(1)=1-0-2=-1<0.
```

Procuramos agora um valor positivo à esquerda de $1$ e outro à direita. Usar potências de $e$ permite calcular exatamente os logaritmos. Os pontos escolhidos são $e^{-2}$ e $e^2$, com:

```math
0<e^{-2}<1<e^2.
```

À esquerda:

```math
F(e^{-2})
=e^{-2}-\ln(e^{-2})-2
=e^{-2}-(-2)-2
=e^{-2}>0.
```

À direita:

```math
F(e^2)
=e^2-\ln(e^2)-2
=e^2-2-2
=e^2-4>0,
```

onde a última desigualdade usa $e>2$, logo $e^2>4$.

### Aplicar Bolzano em dois intervalos

A função é contínua em $[e^{-2},1]$, e os valores nos extremos têm sinais opostos. Existe, portanto:

```math
c_1\in(e^{-2},1)
\quad\text{tal que}\quad F(c_1)=0.
```

Também é contínua em $[1,e^2]$, e os valores nos extremos voltam a ter sinais opostos. Existe:

```math
c_2\in(1,e^2)
\quad\text{tal que}\quad F(c_2)=0.
```

Como um ponto está estritamente abaixo de $1$ e o outro estritamente acima, temos $c_1\ne c_2$.

**Conclusão para escrever:**

> A continuidade de $F$ e os sinais $F(e^{-2})>0$, $F(1)<0$ e $F(e^2)>0$ permitem aplicar Bolzano em $[e^{-2},1]$ e $[1,e^2]$. Obtemos uma raiz em cada um dos intervalos abertos disjuntos $(e^{-2},1)$ e $(1,e^2)$. Logo, a equação tem pelo menos duas raízes distintas.

Esta prova estabelece a existência de pelo menos duas raízes; não afirma que sejam exatamente duas. O método foi explicado com ajuda, e ainda não foi registada uma nova tentativa do aluno a reconstruir esta prova.

## 11. Pontos de atenção para retomar

- Um cancelamento válido fora de um ponto ajuda a calcular o limite, mas não redefine automaticamente a função nesse ponto nem apaga as outras restrições do domínio.
- Uma função por ramos atribui o valor no ponto através do ramo que o inclui. Os limites usam a expressão válida nas proximidades correspondentes.
- A continuidade em $[0,1]$ usa a aproximação pelo interior: $0^+$ no extremo esquerdo e $1^-$ no extremo direito.
- Em $\max(f,g)$, comparamos $f(x)$ e $g(x)$ para a mesma entrada. A prova não depende da igualdade $f(a)=g(a)$.
- Uma hipótese de continuidade num ponto justifica uma conclusão nesse ponto; não se deve ampliar a conclusão a todo o domínio sem hipóteses adicionais.
- Para Bolzano, escolher uma função contínua no intervalo inteiro e justificar a mudança de sinal. Duas raízes distintas requerem uma separação que impeça contar a mesma raiz duas vezes.

As resoluções e explicações registadas não equivalem, por si só, a domínio autónomo de todos os métodos. O estado das tentativas e o ponto de retoma devem seguir o [registo de progresso](../PROGRESSO.md).
