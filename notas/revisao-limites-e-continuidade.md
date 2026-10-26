# Revisão curta — limites e continuidade

Preparada em **26 de outubro de 2026**, para leitura no final da sessão. O aluno indicou um mini teste no dia seguinte, sobre limites e continuidade, com duração aproximada de 15 minutos. Este resumo não presume as perguntas nem os critérios do docente e não acrescenta exercícios para resolver.

[Índice](../README.md) · [Teoremas e exercícios 3.23–3.27](bolzano-weierstrass-e-pontos-fixos.md) · [Definição ε–δ](continuidade-epsilon-delta.md)

## 1. Antes das contas: ponto, domínio e lado

Identificar para onde tende a variável e quais os pontos do domínio usados nessa aproximação. Numa função por ramos, escolher a expressão válida no lado considerado.

Ao mudar de variável, transformar também a aproximação. Por exemplo:

```math
u=\frac1x:
\qquad x\to0^+\Rightarrow u\to+\infty,
\qquad x\to+\infty\Rightarrow u\to0^+.
```

Não confundir uma aproximação pela esquerda com um valor negativo da função. Os sinais das entradas e das saídas têm de ser estudados separadamente.

## 2. Composição: primeiro o limite interior

Se $g(x)\to L\in\mathbb R$ e $f$ é contínua em $L$, com a composição definida nas proximidades consideradas:

```math
\lim_{x\to a}f(g(x))=f(L).
```

Não é um produto de limites. A propriedade vale para funções contínuas em geral, não apenas para funções inversas.

```math
\lim_{x\to+\infty}\sin(1/x)=\sin0=0.
```

Já quando $x\to0$, o argumento $1/x$ não converge para um número real e $\sin(1/x)$ oscila sem limite. Não se substitui «infinito» no seno como se fosse um número.

## 3. Reconhecer a forma antes de escolher o método

| Situação | Caminho a considerar |
| --- | --- |
| Substituição dá um valor definido numa expressão contínua | Substituir diretamente. |
| Forma 0/0 com fatores algébricos | Fatorizar e cancelar fatores não nulos fora do ponto. |
| Diferença de raízes | Multiplicar pelo conjugado e usar a diferença de quadrados. |
| Quociente no infinito | Dividir por um termo dominante adequado. |
| Numerador tende a um valor não nulo e denominador tende a zero | Estudar os sinais e os limites laterais. |
| Oscilação multiplicada por uma quantidade que tende a zero | Procurar um enquadramento global da parcela oscilante. |

L’Hôpital só deve ser usado sob as suas hipóteses, após reconhecer uma forma adequada, como $0/0$ ou $\infty/\infty$. Derivam-se numerador e denominador separadamente; não se usa a fórmula da derivada de um quociente.

```math
(\sqrt{x})'=\frac1{2\sqrt{x}},
\qquad x>0.
```

No exemplo trabalhado:

```math
\frac{\sqrt{x}}{x-1}
=\frac{\sqrt{x}/x}{(x-1)/x}
=\frac{1/\sqrt{x}}{1-1/x}
\longrightarrow0\quad(x\to+\infty).
```

Esta transformação divide numerador e denominador por $x$; o quociente mantém o mesmo valor.

## 4. Limites notáveis: o argumento tem de tender a zero

```math
\begin{aligned}
\lim_{u\to0}\frac{\sin u}{u}
&=\lim_{u\to0}\frac{\tan u}{u}=1,\\
\lim_{u\to0}\frac{\arcsin u}{u}
&=\lim_{u\to0}\frac{\arctan u}{u}=1.
\end{aligned}
```

Fazer coincidir o argumento com o denominador, retirando os fatores constantes necessários. Por exemplo, para $k\ne0$:

```math
\frac{\sin(kx)}x
=k\,\frac{\sin(kx)}{kx}\longrightarrow k
\quad(x\to0).
```

Se $k=0$, a expressão é zero para $x\ne0$ e o mesmo resultado segue diretamente. Não se invoca o limite notável $\sin u/u\to1$ quando $u\to\infty$.

## 5. Oscilação, confronto e sucessões

Para $x\ne0$:

```math
|x\sin(1/x)|\leq|x|\longrightarrow0,
\qquad
|x^2\sin(1/x)|\leq x^2\longrightarrow0
\quad(x\to0).
```

O confronto justifica estes limites. Não é necessário atribuir um limite ao seno oscilante.

No confronto, as duas funções que enquadram têm de tender ao mesmo valor para concluir esse limite. Extremos com limites diferentes deixam o teste inconclusivo.

Para provar a inexistência do limite de $\sin(1/x)$ em zero, podem escolher-se ângulos que deem sempre 1 e sempre $-1$:

```math
\frac1{x_n}=\frac\pi2+2n\pi,
\qquad
\frac1{y_n}=\frac{3\pi}2+2n\pi.
```

Isolam-se $x_n$ e $y_n$ invertendo cada membro inteiro. Quando $n\to+\infty$, as duas sucessões tendem a $0^+$, mas as imagens têm limites diferentes.

Duas sucessões com resultados diferentes refutam um limite; duas com resultados iguais não provam existência. Nos limites das imagens $f(x_n)$, o índice é $n\to+\infty$.

Também não se subtraem formalmente limites quando um deles não existe. Estudar uma parcela convergente separadamente é válido, mas a conclusão sobre a função inteira deve ser justificada, por exemplo, por sucessões ou contradição.

## 6. Continuidade e prolongamento

Numa junção interior, a condição é:

```math
\lim_{x\to a^-}f(x)
=\lim_{x\to a^+}f(x)
=f(a),
```

com valor real e finito. O valor $f(a)$ vem do ramo que inclui o ponto.

Nos extremos de um intervalo fechado, a continuidade da restrição usa a aproximação pelo interior. Para expressões polinomiais, a continuidade pode ser justificada diretamente, sem calcular todos os limites ponto a ponto.

Para prolongar por continuidade a um ponto excluído, calcular o limite: se existir e for finito, esse é o único valor a acrescentar. Um cancelamento não preenche automaticamente o ponto nem apaga as restrições do domínio original.

«Por resultar de operações e composições de funções contínuas» é uma justificação geral válida onde as operações estão definidas. Nas junções de uma função por ramos, é preciso verificar também a coincidência com o valor no ponto.

## 7. Bolzano e Weierstrass

**Bolzano para zeros:** continuidade em $[a,b]$ e $f(a)f(b)<0$ garantem pelo menos um zero em $(a,b)$. Se um extremo já vale zero, já existe uma raiz, sem precisar da hipótese de produto estritamente negativo.

Para duas raízes distintas, garantir uma em cada um de dois intervalos abertos disjuntos. Para procurar $f(c)=c$, definir $h(x)=f(x)-x$ e procurar um zero de $h$.

**Weierstrass:** uma função contínua num intervalo fechado e limitado atinge um máximo e um mínimo. Não exige calcular os valores nos extremos do intervalo para provar existência; também não garante que o máximo e o mínimo sejam atingidos nessas pontas.

Os valores máximo e mínimo, quando existem, são únicos; os pontos onde são atingidos podem ser vários. «Pelo menos um ponto de máximo» é uma formulação correta.

A impossibilidade de aplicar um teorema não demonstra que a sua conclusão seja falsa: significa que esse teorema não a garante nessas condições.

## 8. Entradas, imagem e módulo

Em $f:A\to B$, o domínio é $A$ e as saídas pertencem a $B$. Não há obrigação de preencher $B$. A igualdade $f(A)=B$ acrescenta precisamente essa exigência sobre a imagem.

Se $f$ é contínua, $|f|$ também é; a recíproca é falsa. Um salto de $-1$ para 1 desaparece ao tomar o módulo. A existência do limite do módulo também não garante a existência do limite da função.

```math
|3|=|-3|=3,
\qquad |ab|=|a|\,|b|,
\qquad |x^2|=|x|^2.
```

Só se substitui $|x|$ por $x$ quando se sabe que $x\geq0$. A função $x\mapsto|x|$ é contínua em zero; o bico do gráfico não é um salto.

## 9. Se aparecer a definição ε–δ

Para continuidade em $a$, dado qualquer $\varepsilon>0$, escolher $\delta>0$ e verificar, para todo $x$ do domínio:

```math
|x-a|<\delta
\Rightarrow
|f(x)-f(a)|<\varepsilon.
```

A escolha de $\delta$ não pode depender do $x$ variável. Nos exemplos da sessão: $\delta=\varepsilon/3$ para $f(x)=3x-2$ em 1, e $\delta=\sqrt{\varepsilon}$ para $g(x)=x^2$ em zero.

Para provar um limite geral $L$, usa-se $0<|x-a|<\delta$ e compara-se $f(x)$ com $L$, não necessariamente com $f(a)$. As [provas completas](continuidade-epsilon-delta.md) mostram a ordem de escrita e a verificação.
