# Análise Matemática I — Continuidade e prolongamento

Apontamentos atualizados em **24 de outubro de 2026**.

[Índice](../README.md) · [Progresso e pendências](../PROGRESSO.md) · [Limites trigonométricos e sucessões](limites-trigonometricos-e-sucessoes.md)

## Origem e âmbito

Base: exercícios 3.12 e 3.13 da [Ficha_exercicios.pdf](../materiais/Ficha_exercicios.pdf) enviada pelo aluno, páginas numeradas 6–7, e resoluções discutidas no chat. As fórmulas usam a notação internacional pedida pelo aluno: $\sin$, $\tan$, $\arcsin$ e $\arctan$.

Foram trabalhadas as alíneas 3.12(a), (b), (c), (d), (f), (g), (h) e (i). A alínea 3.12(e) foi retomada apenas para interpretar o pedido do 3.13(a); os cálculos desse prolongamento ficam pendentes. Não se presume resolução das restantes questões da ficha.

## 1. O que significa estudar a continuidade

A ideia é comparar o comportamento da função perto de um ponto com o valor atribuído à função nesse ponto. Para os pontos estudados nesta ficha, a continuidade em $a$ exige que $a$ pertença ao domínio e que:

```math
\lim_{x\to a}f(x)=f(a).
```

O limite é tomado dentro do domínio. Quando podemos aproximar $a$ pelos dois lados, a condição escreve-se:

```math
\lim_{x\to a^-}f(x)
=\lim_{x\to a^+}f(x)
=f(a).
```

O valor comum tem de ser real e finito. Um único limite lateral diferente de $f(a)$, infinito ou inexistente já basta para excluir a continuidade em $a$. Porém, conhecer apenas um lateral não permite, em geral, atribuir esse resultado ao limite bilateral.

Se $f(a)$ não está definido, a função original não pode ser contínua nesse ponto. Ainda assim, pode ser contínua em **todo o seu domínio**. A possibilidade de lhe atribuir um valor em $a$ que complete a continuidade é uma pergunta adicional: a do prolongamento.

### Uma ordem de trabalho

1. Determinar o domínio, respeitando cada expressão e as condições dos ramos.
2. Identificar as regiões onde a continuidade resulta das operações e composições de funções contínuas.
3. Nas junções de ramos que pertencem ao domínio, comparar os limites pertinentes com o valor da função.
4. Se for pedido um prolongamento num ponto excluído, verificar se existe um limite real e finito nesse ponto.

Não é necessário calcular um limite em cada ponto onde os teoremas sobre operações e composições já garantem a continuidade.

### Justificação reutilizável, com as condições necessárias

> A função é contínua no conjunto considerado por ser obtida através de operações e composições de funções contínuas, respeitando as condições de definição dessas operações.

Quando possível, concretizar a operação: soma, diferença, produto, quociente com denominador não nulo ou composição com argumentos dentro do domínio da função exterior. Para o logaritmo real, o argumento tem de ser positivo; para uma raiz quadrada, o radicando tem de ser não negativo.

Esta frase não substitui a verificação das junções de uma função por ramos.

O domínio não precisa de ser um intervalo fechado. Por exemplo:

```math
\mathbb R\setminus\{0\}
=(-\infty,0)\cup(0,+\infty).
```

Este conjunto é a união de dois intervalos abertos, e não um intervalo fechado.

## 2. 3.12(a): quociente de polinómios

```math
f(x)=\frac{x+1}{x^3+x}
=\frac{x+1}{x(x^2+1)}.
```

Como $x^2+1>0$ para todo $x\in\mathbb R$, o denominador só se anula em zero. Assim:

```math
D_f=\mathbb R\setminus\{0\}.
```

A função é contínua em todo o seu domínio, por ser um quociente de polinómios com denominador não nulo nesse conjunto.

Perto de zero, o numerador é positivo e tende a $1$. O denominador tem o sinal de $x$, pois $x^2+1$ é positivo. Logo:

```math
\lim_{x\to0^+}f(x)=+\infty,
\qquad
\lim_{x\to0^-}f(x)=-\infty.
```

O limite calculado pela direita deve conservar o sinal $+$ na notação; não é o limite bilateral. Além de $f(0)$ não estar definido, nenhum valor real atribuído em zero poderia tornar a função contínua nesse ponto. Para excluir essa possibilidade, um só dos laterais infinitos já bastava.

## 3. 3.12(b): valor absoluto e exponencial

```math
f(x)=|x|e^{-|x|},
\qquad D_f=\mathbb R.
```

A função $x\mapsto|x|$ é contínua em $\mathbb R$. A função $x\mapsto e^{-|x|}$ é contínua por composição da exponencial com $-|x|$. O produto é, portanto, contínuo em todo $\mathbb R$, incluindo zero.

## 4. 3.12(c): combinar as condições do domínio

```math
f(x)=\sqrt{x}-\frac1{x^2+x}.
```

A raiz quadrada exige $x\geq0$. A fração exige:

```math
x^2+x=x(x+1)\ne0,
\qquad x\ne0,\quad x\ne-1.
```

Temos de satisfazer as condições simultaneamente. Como $x\geq0$ já exclui $-1$, resta:

```math
D_f=\{x\in\mathbb R:x>0\}=(0,+\infty).
```

Depois de escrever $x>0$, acrescentar $x\ne0$ é redundante. A função é contínua em $(0,+\infty)$ pelas operações entre funções contínuas, com a raiz definida e o denominador não nulo nesse conjunto.

## 5. 3.12(d): o argumento do logaritmo

```math
f(x)=x\ln(\sin^2x).
```

A condição do logaritmo é:

```math
\sin^2x>0
\quad\Longleftrightarrow\quad
\sin x\ne0.
```

Um quadrado é positivo quando a sua base é diferente de zero; a base pode ser positiva ou negativa. Por isso, esta condição não se resolve impondo $x>k\pi$.

Os zeros do seno são os múltiplos inteiros de $\pi$:

```math
\sin x=0
\quad\Longleftrightarrow\quad
x=k\pi\text{ para algum }k\in\mathbb Z.
```

São esses pontos que excluímos:

```math
D_f=\mathbb R\setminus\{k\pi:k\in\mathbb Z\}.
```

Por outras palavras, o domínio contém todos os reais exceto $\ldots,-2\pi,-\pi,0,\pi,2\pi,\ldots$. A periodicidade de $\sin^2x$ explica a repetição desses pontos excluídos.

Em cada ponto do domínio, $\sin^2x$ é positivo, a composição com o logaritmo é contínua e o produto por $x$ preserva a continuidade. Logo, $f$ é contínua em todo o seu domínio; em particular, em cada intervalo:

```math
(k\pi,(k+1)\pi),\qquad k\in\mathbb Z.
```

## 6. 3.12(f): quociente e valor absoluto

```math
f(x)=\left|\frac{x-1}{x^2+1}\right|,
\qquad D_f=\mathbb R.
```

Como $x^2+1>0$ para todo real $x$, o quociente está definido e é contínuo em todo $\mathbb R$. A composição com o valor absoluto também é contínua, pelo que $f$ é contínua em todo $\mathbb R$.

Na conferência visual da ficha, confirmou-se que o valor absoluto envolve o quociente inteiro. Estas barras tinham sido omitidas na transcrição usada no chat; a conclusão sobre domínio e continuidade mantém-se.

## 7. Domínios de funções por ramos

Cada expressão só impõe as suas restrições na região em que esse ramo é usado. Para determinar o domínio:

1. Em cada ramo, combinar a condição do ramo com o domínio da respetiva expressão.
2. Reunir os conjuntos assim obtidos.

Isto é uma união dos domínios condicionados de cada ramo, não a aplicação simultânea de todos os denominadores a todos os reais.

Uma expressão poder falhar num ponto que pertence a outro ramo não obriga a excluir esse ponto da função completa. Do mesmo modo, um ramo que atribui diretamente um valor num ponto pode completar o domínio, mesmo que a expressão do outro ramo não esteja definida aí.

## 8. 3.12(g): simplificar sem alterar o valor no ponto

```math
f(x)=
\begin{cases}
\dfrac{x^2-16}{x-4},&x\ne4,\\
1,&x=4.
\end{cases}
```

O domínio é $\mathbb R$: o primeiro ramo cobre todos os reais diferentes de $4$, e o segundo define $f(4)=1$.

Para $x\ne4$, podemos fatorizar e cancelar:

```math
\frac{x^2-16}{x-4}
=\frac{(x-4)(x+4)}{x-4}
=x+4.
```

A função completa passa a escrever-se:

```math
f(x)=
\begin{cases}
x+4,&x\ne4,\\
1,&x=4.
\end{cases}
```

O cancelamento não muda o valor definido pelo segundo ramo. Como a expressão $x+4$ vale dos dois lados de $4$:

```math
\lim_{x\to4^-}f(x)
=\lim_{x\to4^+}f(x)
=4+4=8,
\qquad f(4)=1.
```

O cálculo correto do limite é $8$, não $5$. Assim, $f$ é contínua em $\mathbb R\setminus\{4\}$ e descontínua em $4$, embora o domínio seja $\mathbb R$.

Bastava um lateral diferente de $f(4)$ para excluir a continuidade. Neste caso, conhecer a mesma expressão em ambos os lados também justifica o limite bilateral.

## 9. 3.12(h): restrições que ficam fora do ramo

Para o parâmetro real $a$, a função é:

```math
f(x)=
\begin{cases}
\dfrac{3x-a}{1-x},&x\leq0,\\
\dfrac{x-a}{1+x},&x>0.
\end{cases}
```

No primeiro ramo, $x\leq0$ implica $1-x\geq1$. O denominador nunca se anula onde esse ramo é usado. No segundo, $x>0$ implica $1+x>1$, pelo que o denominador também nunca se anula na região correspondente. Portanto:

```math
D_f=(-\infty,0]\cup(0,+\infty)=\mathbb R.
```

Não se excluem $-1$ nem $1$: em $-1$ usamos o primeiro ramo, cujo denominador vale $2$; em $1$ usamos o segundo ramo, cujo denominador também vale $2$.

Cada expressão racional é contínua na sua região. Na junção, calculamos os laterais com os ramos correspondentes:

```math
\lim_{x\to0^-}f(x)
=\frac{3\cdot0-a}{1-0}=-a,
\qquad
\lim_{x\to0^+}f(x)
=\frac{0-a}{1+0}=-a.
```

O valor no ponto vem do primeiro ramo, porque é esse que inclui $x=0$:

```math
f(0)=\frac{3\cdot0-a}{1-0}=-a.
```

Os dois limites laterais são iguais a $f(0)$. A função é contínua em todo $\mathbb R$ para qualquer $a\in\mathbb R$. Não foi necessário escolher um valor especial do parâmetro.

## 10. 3.12(i): confronto com a função inteira

```math
f(x)=
\begin{cases}
x^2\sin(1/x)-2x,&x\ne0,\\
0,&x=0.
\end{cases}
```

O domínio é $\mathbb R$. Para $x\ne0$, a continuidade resulta das operações e composições envolvidas. Falta estudar a junção em zero.

O aluno apresentou a seguinte prova com a função inteira, após discutir o método do confronto. Partimos de:

```math
-1\leq\sin(1/x)\leq1,\qquad x\ne0.
```

Multiplicamos por $x^2>0$ e depois subtraímos $2x$ em todos os membros:

```math
-x^2\leq x^2\sin(1/x)\leq x^2,
```

```math
-x^2-2x
\leq x^2\sin(1/x)-2x
\leq x^2-2x.
```

Os extremos têm o mesmo limite:

```math
\lim_{x\to0}(-x^2-2x)=0,
\qquad
\lim_{x\to0}(x^2-2x)=0.
```

Pelo teorema do confronto:

```math
\lim_{x\to0}f(x)=0=f(0).
```

As desigualdades são válidas para valores positivos e negativos de $x$, por isso o argumento já demonstra o limite bilateral. Também se pode escrever explicitamente que os dois limites laterais são zero.

A conclusão completa é:

> Para $x\ne0$, a função é contínua pelas operações e composições de funções contínuas. Em zero, o confronto mostra que o limite é igual a $f(0)$. Logo, $f$ é contínua em todo $\mathbb R$.

### Por que o seno oscilante deixou de impedir o limite?

No exercício 3.10(a), $\sin(1/x)$ assume repetidamente os valores $1$ e $-1$ arbitrariamente perto de zero. Aqui, a parcela oscilante está multiplicada por $x^2$:

```math
\left|x^2\sin(1/x)\right|\leq x^2\longrightarrow0.
```

A oscilação fica entre duas quantidades que se aproximam de zero. Uma função limitada multiplicada por uma função que tende a zero tende a zero; o confronto justifica esta propriedade.

Se escolhermos as sucessões do 3.10(a), o seno continua a valer $1$ e $-1$, mas as imagens pela função completa são:

```math
f(x_n)=x_n^2-2x_n\longrightarrow0,
\qquad
f(y_n)=-y_n^2-2y_n\longrightarrow0.
```

Nestes limites de sucessões, escrevemos $n\to+\infty$. É ao percorrer os índices que $x_n$ e $y_n$ se aproximam de zero. Não se substitui essa notação por $x\to0$ mantendo a expressão $f(x_n)$.

Duas sucessões particulares com limites diferentes nas imagens refutam a existência de um limite. Duas com o mesmo limite não chegam para o provar. Para demonstrar a existência pelo critério das sucessões, seria preciso justificar o mesmo resultado para **toda** a sucessão de pontos do domínio, diferentes de zero, que tende a zero. O confronto já cobre todas as aproximações, sem escolher sucessões especiais.

### A tentativa com mudança de variável

A identidade seguinte é válida para $x\ne0$:

```math
x^2\sin(1/x)
=x\,\frac{\sin(1/x)}{1/x}.
```

Contudo, se $u=1/x$ e $x\to0^+$, então $u\to+\infty$. Não se pode invocar o limite notável $\sin u/u\to1$, que exige $u\to0$. No infinito, $\sin u/u\to0$ por confronto; esse caminho também permite obter zero, mas exige mais transformações do que o enquadramento direto acima.

A forma habitual de L’Hôpital para indeterminações $0/0$ ou $\infty/\infty$ não se aplica diretamente ao quociente $\sin(1/x)/(1/x^2)$: o numerador oscila, enquanto o denominador tende a $+\infty$. Isto não afirma a impossibilidade de qualquer reformulação ou versão mais geral da regra. Para esta resolução, o confronto é suficiente.

## 11. 3.13(a): interpretar o prolongamento por continuidade

**Estado no final de 24 de outubro:** enunciado interpretado; cálculo dos limites laterais ainda pendente. **Atualização de 25 de outubro:** o aluno calculou os dois laterais e concluiu que não existe prolongamento contínuo. A resolução está nas [notas de prolongamentos e Bolzano](prolongamentos-e-bolzano.md).

O exercício pede para analisar a existência de um prolongamento por continuidade à origem da função da alínea 3.12(e):

```math
f(x)=\frac1{1-e^{1/x}}.
```

A expressão não define $f(0)$, pois contém $1/x$. «Prolongar à origem» significa acrescentar um valor em $x=0$, mantendo os valores originais nos restantes pontos. «Por continuidade» exige que esse valor torne a função contínua em zero.

Procuramos, portanto, um número real $K$ para construir:

```math
F(x)=
\begin{cases}
\dfrac1{1-e^{1/x}},&x\ne0,\\
K,&x=0.
\end{cases}
```

O pedido equivale à pergunta: **existe um valor real de $K$ para o qual $F$ é contínua em zero?** A condição a testar é:

```math
\lim_{x\to0^-}f(x)
=\lim_{x\to0^+}f(x)
=K.
```

Se os dois laterais forem iguais a um mesmo número real $L$, escolhemos $K=L$. Se forem diferentes, infinitos ou algum não existir, nenhum valor real de $K$ produz continuidade em zero. O enunciado pede analisar a existência; não garante que um valor adequado exista.

«À origem» refere-se aqui ao ponto $x=0$; não impõe $K=0$ nem exige que o gráfico passe por $(0,0)$.

O passo previsto para 25 de outubro foi realizado: os laterais do 3.13(a) são diferentes. O 3.13(b) também foi discutido nessa sessão, com prolongamento contínuo obtido ao atribuir o valor zero na origem. Ver as [resoluções de 3.13(a,b)](prolongamentos-e-bolzano.md).

## 12. Evidências da sessão de 24 de outubro

| Exercício | O que foi observado na conversa |
| --- | --- |
| 3.12(a) | Domínio e lateral direito apresentados corretamente; afinada com ajuda a distinção entre continuidade no domínio e prolongamento em zero. |
| 3.12(b), (c), (f) | Domínios e justificações apresentados pelo aluno e conferidos; em (c), esclarecida a redundância de acrescentar $x\ne0$ depois de $x>0$. Na preparação destas notas, reposto o valor absoluto da alínea (f) após conferir a ficha. |
| 3.12(d) | Condição do logaritmo identificada; a passagem de $\sin^2x>0$ para a exclusão dos múltiplos de $\pi$ foi corrigida com ajuda. |
| 3.12(g) | Fatorização e critério de continuidade apresentados; domínio reconsiderado pelo aluno e cálculo do limite corrigido para $8$. |
| 3.12(h) | Laterais e valor no ponto calculados como $-a$; domínio corrigido com ajuda, respeitando as regiões dos ramos. |
| 3.12(i) | Método discutido com ajuda; depois o aluno reconstruiu uma prova correta pelo confronto aplicado à função inteira. Persistiram dúvidas de notação ao retomar sucessões. |
| 3.13(a) | Em 24 de outubro, o aluno relacionou prolongamento com a escolha de uma constante num ramo; o significado do pedido foi explicado, ainda sem tentativa dos laterais. Em 25 de outubro, apresentou os laterais e a conclusão correta. |

Estas evidências não equivalem a domínio autónomo de todo o tema. Para o ponto atual de retoma e as pendências, consultar [PROGRESSO.md](../PROGRESSO.md).
