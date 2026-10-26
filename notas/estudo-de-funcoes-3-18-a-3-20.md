# Análise Matemática I — Estudo de funções: 3.18 a 3.20

Apontamentos da sessão de **25 de outubro de 2026**.

[Índice](../README.md) · [Progresso e pendências](../PROGRESSO.md) · [Continuidade e prolongamento](continuidade-e-prolongamento.md) · [Limites trigonométricos e sucessões](limites-trigonometricos-e-sucessoes.md)

Fonte: [ficha de exercícios fornecida pelo aluno](../materiais/Ficha_exercicios.pdf), página numerada 8, correspondente à página física 10 do PDF. Estas notas guardam os argumentos discutidos e as correções relevantes; não antecipam as partes que ficaram sem tentativa registada.

## 1. Ficha 3.18 — continuidade, imagem, extremos e limites

A função está definida em todo $\mathbb R$ por:

```math
f(x)=\begin{cases}
0,&x\leq-1,\\
2e^{x-1},&-1<x<1,\\
r\sin\left(\dfrac{\pi x}{2}\right),&x\geq1.
\end{cases}
```

As condições dos ramos cobrem todos os reais. No interior de cada região, as expressões são contínuas pelas operações e composições envolvidas. As junções a verificar são $-1$ e $1$.

### a) Escolher r para obter continuidade em 1

Pela esquerda de $1$, usamos o ramo exponencial:

```math
\lim_{x\to1^-}f(x)=2e^{1-1}=2.
```

Pela direita, e no próprio ponto, usamos o ramo trigonométrico:

```math
\lim_{x\to1^+}f(x)
=r\sin\left(\frac\pi2\right)=r,
\qquad
f(1)=r.
```

Portanto, a igualdade dos dois laterais com o valor da função exige:

```math
r=2.
```

As restantes conclusões sobre esta função consideram esse valor do parâmetro.

### b) Estudar a outra junção

Em $x=-1$, o valor da função pertence ao primeiro ramo:

```math
f(-1)=0,
\qquad
\lim_{x\to-1^-}f(x)=0.
```

Pela direita, o ramo exponencial dá:

```math
\lim_{x\to-1^+}f(x)
=2e^{-1-1}
=\frac2{e^2}.
```

Como $2/e^2\ne0$, os laterais são diferentes. Assim, para $r=2$, a função é descontínua em $-1$ e contínua em todos os restantes pontos:

```math
\text{Conjunto de continuidade}=\mathbb R\setminus\{-1\}.
```

O domínio continua a ser $\mathbb R$: a descontinuidade em $-1$ não retira esse ponto do domínio.

### c) Conjunto dos valores assumidos e extremos

Na pergunta da ficha intitulada «contradomínio», determinamos o conjunto dos valores efetivamente assumidos, isto é, a **imagem**. Convém distinguir este conjunto do conjunto de chegada $\mathbb R$ declarado em $f:\mathbb R\to\mathbb R$.

Analisamos as imagens dos ramos e reunimos os resultados:

| Região de entrada | Expressão | Valores assumidos |
| --- | --- | --- |
| $x\leq-1$ | $0$ | $\{0\}$ |
| $-1<x<1$ | $2e^{x-1}$ | $(2/e^2,2)$ |
| $x\geq1$ | $2\sin(\pi x/2)$ | $[-2,2]$ |

No ramo exponencial, $-2<x-1<0$. Como a exponencial é estritamente crescente, os valores variam entre $2/e^2$ e $2$, sem atingir esses extremos **nesse ramo**.

No ramo trigonométrico, o seno fica entre $-1$ e $1$, pelo que os valores ficam entre $-2$ e $2$. Além disso:

```math
f(1)=2\sin\left(\frac\pi2\right)=2,
\qquad
f(3)=2\sin\left(\frac{3\pi}2\right)=-2.
```

O ramo é contínuo em $[1,3]$ e assume os dois extremos; portanto, assume também todos os valores intermédios. A imagem da função completa é:

```math
\mathrm{Im}(f)=[-2,2].
```

Usando apenas a notação dos extremos:

```math
\sup f(\mathbb R)=\max f(\mathbb R)=2,
\qquad
\inf f(\mathbb R)=\min f(\mathbb R)=-2.
```

Há máximo e mínimo porque os valores $2$ e $-2$ são efetivamente atingidos. Supremo e ínfimo são as melhores cotas; não exigem, por definição, que a função as atinja.

### d) Limites nos dois infinitos

Para valores suficientemente negativos de $x$, estamos sempre no ramo constante. Logo:

```math
\lim_{x\to-\infty}f(x)=0.
```

Quando $x\to+\infty$, usamos o ramo $2\sin(\pi x/2)$. Para provar a inexistência do limite, escolhemos entradas que façam o seno valer alternadamente $1$ e $-1$.

Para $n=1,2,3,\ldots$, começamos pelos ângulos:

```math
\frac{\pi x_n}{2}=\frac\pi2+2n\pi
\quad\Longrightarrow\quad x_n=1+4n,
```

```math
\frac{\pi y_n}{2}=\frac{3\pi}2+2n\pi
\quad\Longrightarrow\quad y_n=3+4n.
```

Ambas as sucessões estão no ramo $x\geq1$ e tendem a $+\infty$, mas:

```math
f(x_n)=2,
\qquad f(y_n)=-2.
```

Se existisse um limite em $+\infty$, estas duas aproximações teriam de produzir o mesmo limite para as imagens. Portanto, $\lim_{x\to+\infty}f(x)$ não existe.

## 2. Ficha 3.19 — prolongamento e funções limitadas

As duas funções têm o domínio indicado no enunciado, $\mathbb R\setminus\{0\}$:

```math
f(x)=e^{-1/x^2},
\qquad
g(x)=x\sin(1/x)-\cos(1/x).
```

### a) Continuidade no domínio

Para $x\ne0$, todos os quocientes estão definidos. As funções exponencial, seno e cosseno são contínuas nos argumentos usados; os produtos, diferenças e composições preservam a continuidade. Assim, ambas as funções são contínuas em cada ponto do seu domínio.

Isso não decide o prolongamento a zero, porque zero não pertence ao domínio original.

### b) Prolongamento de f

Quando $x\to0$ por qualquer lado, $x^2$ é positivo e tende a zero. Logo:

```math
\frac1{x^2}\to+\infty,
\qquad -\frac1{x^2}\to-\infty,
\qquad e^{-1/x^2}\to0.
```

Existe, portanto, prolongamento contínuo a zero, atribuindo o valor $0$ nesse ponto:

```math
F(x)=\begin{cases}
e^{-1/x^2},&x\ne0,\\
0,&x=0.
\end{cases}
```

A igualdade $\lim_{x\to0}f(x)=F(0)$ justifica a continuidade do prolongamento em zero.

### b) A parcela x vezes seno de um sobre x

Para estudar $g$, podemos começar separadamente pela parcela:

```math
u(x)=x\sin(1/x).
```

A estimativa

```math
|u(x)|=|x|\,|\sin(1/x)|\leq|x|
```

mostra, pelo confronto, que $u(x)\to0$ quando $x\to0$. Em forma de enquadramento, também podemos escrever $-|x|\leq u(x)\leq|x|$.

O método do aluno de estudar esta parcela por confronto **é válido**. Falta justificar o que acontece ao cosseno e à diferença completa; não se podem subtrair formalmente limites quando um deles não existe.

### b) Inexistência do limite de g por sucessões

Para obter valores exatos, procuramos ângulos em que o seno seja zero e o cosseno seja $1$ ou $-1$.

Para $n=1,2,3,\ldots$, escolhemos:

```math
\frac1{x_n}=2\pi n
\quad\Longrightarrow\quad
x_n=\frac1{2\pi n}\longrightarrow0^+,
```

```math
\frac1{y_n}=\pi+2\pi n
\quad\Longrightarrow\quad
y_n=\frac1{\pi+2\pi n}\longrightarrow0^+.
```

Ao substituir na função **inteira**:

```math
g(x_n)=x_n\sin(2\pi n)-\cos(2\pi n)
=x_n\cdot0-1=-1,
```

```math
g(y_n)=y_n\sin(\pi+2\pi n)-\cos(\pi+2\pi n)
=y_n\cdot0-(-1)=1.
```

As entradas tendem ao mesmo ponto, mas as imagens têm limites diferentes. Logo, $g$ não tem limite em zero e não admite prolongamento contínuo nesse ponto. As duas sucessões até se aproximam pela direita, pelo que já excluem a existência do limite lateral direito.

A notação dos limites das imagens é:

```math
\lim_{n\to+\infty}g(x_n)=-1,
\qquad
\lim_{n\to+\infty}g(y_n)=1.
```

Quem cresce sem limite é o índice $n$; os termos $x_n$ e $y_n$ tendem a zero. Não se escreve $n\to0$ para percorrer estas sucessões.

### b) Como completar o argumento do aluno por contradição

As mesmas sucessões mostram que $\cos(1/x)$ não tem limite em zero: os valores do cosseno são, respetivamente, $1$ e $-1$.

Já sabemos por confronto que $u(x)=x\sin(1/x)\to0$. Suponhamos que $g(x)$ tivesse um limite real $L$. Pela identidade:

```math
\cos(1/x)=u(x)-g(x),
```

as regras dos limites dariam então $\cos(1/x)\to0-L=-L$. Isso contradiz a inexistência do limite do cosseno. Logo, $g$ não pode ter limite real em zero.

Este argumento justifica a conclusão sem escrever uma subtração com um «limite inexistente». A demonstração direta por sucessões acima chega à mesma conclusão.

### c) Limitação de f

Para todo $x\ne0$, o expoente $-1/x^2$ é estritamente negativo. Portanto:

```math
0<e^{-1/x^2}<1.
```

Assim, $f$ é limitada inferiormente por $0$ e superiormente por $1$. O expoente percorre $(-\infty,0)$, pelo que a imagem é $(0,1)$: os extremos não são atingidos no domínio original. De facto, $f(x)\to0$ quando $x\to0$, enquanto $f(x)\to1$ quando $x\to+\infty$ ou $x\to-\infty$.

### c) Limitação de g — revisão dos fundamentos adiada

Foi apresentada uma estimativa global usando $|\sin t|\leq|t|$, válida para $t\in\mathbb R$ em radianos. Ao tomar $t=1/x$, obtemos $|\sin(1/x)|\leq|1/x|$: o seno é substituído por uma cota superior, numa desigualdade, não numa igualdade.

A desigualdade triangular aplica-se à diferença porque $|A-B|=|A+(-B)|\leq|A|+|-B|=|A|+|B|$. Com estas duas propriedades:

```math
\begin{aligned}
|g(x)|
&\leq|x\sin(1/x)|+|\cos(1/x)|\\
&\leq|x|\left|\frac1x\right|+1\\
&=2,\qquad x\ne0.
\end{aligned}
```

Isto demonstra que $g$ é limitada. A desigualdade $|g(x)|\leq2$ fornece uma cota; **não identifica a imagem exata** nem afirma que $2$ ou $-2$ sejam atingidos.

**Estado da aprendizagem:** o aluno decidiu adiar a revisão de $|\sin t|\leq|t|$ e da desigualdade triangular. A estimativa fica registada como argumento apresentado; os seus fundamentos permanecem pendentes de revisão. Não se considera que tenham sido dominados autonomamente.

### Limites de g no infinito

Para $u=1/x$, temos:

```math
g(x)=\frac{\sin u}{u}-\cos u.
```

Se $x\to+\infty$, então $u\to0^+$; se $x\to-\infty$, então $u\to0^-$. Em ambos os casos, o limite notável e a continuidade do cosseno dão:

```math
\lim_{x\to+\infty}g(x)
=\lim_{x\to-\infty}g(x)
=1-1=0.
```

Estes limites são compatíveis com a limitação, mas a estimativa anterior é a justificação global de que os valores ficam limitados em todo o domínio.

## 3. Ficha 3.20 — domínio e limites já trabalhados

A função é:

```math
f(x)=\frac{\sqrt{x}}{x-1}.
```

### a) Domínio como união de intervalos disjuntos

A raiz exige $x\geq0$. O denominador exige $x\ne1$. Combinando as duas condições:

```math
D_f=[0,1)\cup(1,+\infty).
```

O ponto $0$ está incluído porque a raiz aí está definida e o denominador não se anula. O ponto $1$ está excluído de ambos os intervalos.

«Disjuntos» significa que os intervalos não têm pontos em comum:

```math
[0,1)\cap(1,+\infty)=\varnothing.
```

Para formar o domínio, usamos a união; a interseção vazia exprime a propriedade de serem disjuntos.

### b) Limite em mais infinito

Dividimos numerador e denominador por $x$, operação válida para $x>0$ no domínio:

```math
\frac{\sqrt{x}}{x-1}
=\frac{\sqrt{x}/x}{(x-1)/x}
=\frac{1/\sqrt{x}}{1-1/x}.
```

O numerador tende a zero e o denominador tende a $1$. Logo:

```math
\lim_{x\to+\infty}\frac{\sqrt{x}}{x-1}=0.
```

Na revisão da derivação, a fórmula correta para a raiz quadrada é:

```math
\left(\sqrt{x}\right)'=\frac1{2\sqrt{x}},
\qquad x>0.
```

### b) Limite pela esquerda de 1

Quando $x\to1^-$, o numerador $\sqrt{x}$ tende a $1$, enquanto $x-1$ é negativo e se aproxima de zero. O quociente é negativo e cresce em módulo sem limite:

```math
\lim_{x\to1^-}\frac{\sqrt{x}}{x-1}=-\infty.
```

### Partes ainda pendentes

- **3.20(b):** limite pela direita de $1$, sem tentativa registada; resultado por determinar na retoma.
- **3.20(c):** conjunto dos valores assumidos, designado «contradomínio» na ficha; ainda sem resolução registada.

Estas partes não são antecipadas nestes apontamentos.

## 4. O que retomar

- Rever, quando o aluno decidir, a desigualdade $|\sin t|\leq|t|$ e a desigualdade triangular usadas na limitação de 3.19(c).
- Manter a distinção entre índice $n\to+\infty$, termos da sucessão que se aproximam do ponto estudado e imagens pela função.
- Preservar o método válido do aluno em 3.19(b): confronto para $x\sin(1/x)$ e justificação da inexistência do limite da diferença por sucessões ou contradição.
- Completar 3.20(b), pela direita de $1$, e 3.20(c), quando forem retomados.

As resoluções aqui registadas não constituem, por si só, evidência de domínio autónomo. O estado das tentativas e os exercícios seguintes constam de [PROGRESSO.md](../PROGRESSO.md).
