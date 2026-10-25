# Análise Matemática I — Limites trigonométricos, laterais e sucessões

Apontamentos atualizados em **24 de outubro de 2026**, a partir das sessões de estudo e da [ficha fornecida pelo aluno](../materiais/Ficha_exercicios.pdf), páginas numeradas 5–6 (páginas físicas 7–8 do PDF).

[Índice](../README.md) · [Progresso](../PROGRESSO.md) · [Limites e radicais](limites-e-radicais.md) · [Continuidade e prolongamento](continuidade-e-prolongamento.md)

As fórmulas usam a notação internacional pedida pelo aluno: $\sin$, $\cos$, $\tan$, $\arcsin$, $\arccos$ e $\arctan$. Os ângulos dos limites notáveis são medidos em **radianos**.

## 1. Escolher o método e identificar a aproximação

Antes de transformar a expressão, registar o ponto e o lado da aproximação. Uma substituição também muda a tendência da variável:

| Aproximação de $x$ | Substituição | Aproximação da nova variável |
| --- | --- | --- |
| $x\to0^+$ | $u=1/x$ | $u\to+\infty$ |
| $x\to0^-$ | $u=1/x$ | $u\to-\infty$ |
| $x\to+\infty$ | $u=1/x$ | $u\to0^+$ |
| $x\to0$ | $u=\sin x$ | $u\to0$ |
| $x\to0$ | $u=\arctan x$ | $u\to0$ |

O limite notável que usamos é:

```math
\lim_{u\to0}\frac{\sin u}{u}=1.
```

Para o reconhecer, o denominador deve coincidir com o argumento do seno, e esse argumento deve tender a zero. A forma visual da fração, por si só, não basta. No infinito, temos outro resultado, obtido por confronto:

```math
\left|\frac{\sin u}{u}\right|\leq\frac1{|u|}\longrightarrow0
\quad\text{quando }u\to+\infty\text{ ou }u\to-\infty.
```

Não conseguir substituir o ponto na expressão não prova que o limite não existe: $\sin x/x$ não está definido em zero, mas tem limite $1$ nesse ponto.

### L’Hôpital e a derivada de um quociente

Uma versão usual da regra de L’Hôpital aplica-se a quocientes com indeterminação $0/0$ ou $\infty/\infty$, sob as hipóteses do teorema. Em particular, as funções devem ser deriváveis na vizinhança considerada, fora do ponto se necessário, a derivada do denominador deve ser não nula, e deve existir o limite do quociente das derivadas. Estas são condições de uma versão suficiente da regra; não constituem uma classificação de todas as variantes possíveis.

Na regra de L’Hôpital, calculamos o limite de $u'/v'$. Não estamos a calcular a derivada da função $u/v$, que é outra expressão:

```math
\left(\frac uv\right)'=\frac{u'v-uv'}{v^2}.
```

Se for necessário aplicar L’Hôpital outra vez, verificar de novo a indeterminação e as hipóteses. Quando um limite notável ou o confronto resolve diretamente o problema, esses métodos também fornecem uma justificação completa.

## 2. Ficha 3.8 — alíneas o), p), q) e r)

### o) Raiz de um quadrado e lado da aproximação

```math
\lim_{x\to0^+}\frac{\sqrt{x^2}}x
=\lim_{x\to0^+}\frac{|x|}x=1.
```

A identidade é $\sqrt{x^2}=|x|$. Pela direita, $x>0$, pelo que $|x|=x$. Pela esquerda, a mesma fração teria limite $-1$.

### p) Conjugado e cancelamento

```math
\lim_{x\to0}\frac{\sqrt{1+x}-\sqrt{1-x}}x.
```

A substituição direta dá $0/0$. Perto de zero, as raízes estão definidas e a soma delas é positiva. Multiplicando pelo conjugado:

```math
\frac{\sqrt{1+x}-\sqrt{1-x}}x
=\frac{(1+x)-(1-x)}{x(\sqrt{1+x}+\sqrt{1-x})}
=\frac{2}{\sqrt{1+x}+\sqrt{1-x}},
\qquad x\ne0.
```

O limite é $2/(1+1)=1$. O sinal no numerador é importante: $(1+x)-(1-x)=2x$.

### q) Diferença de raízes no infinito

```math
\lim_{x\to+\infty}\left(\sqrt{x^2-2}-\sqrt{x^2+3}\right).
```

Pondo $A=\sqrt{x^2-2}$ e $B=\sqrt{x^2+3}$, a identidade $(A-B)(A+B)=A^2-B^2$ permite racionalizar. O cálculo correto é:

```math
A^2-B^2=(x^2-2)-(x^2+3)=-5.
```

Assim,

```math
\sqrt{x^2-2}-\sqrt{x^2+3}
=\frac{-5}{\sqrt{x^2-2}+\sqrt{x^2+3}}
\longrightarrow0.
```

O numerador é $-5$, não $1$ nem $0$. O denominador tende a $+\infty$, e a expressão aproxima-se de zero por valores negativos. Mesmo que o numerador fosse $1$, uma constante dividida por uma quantidade positiva que cresce sem limite tenderia a zero. Escritas como $1/(+\infty)$ são apenas indicações informais de comportamento; infinito não é um número real pelo qual se divide.

### r) Seno hiperbólico e L’Hôpital

Esta resolução foi apresentada no histórico recuperado; a sua execução autónoma pelo aluno não foi verificada.

```math
\lim_{x\to0}\frac{\sinh x-\sin x}{x^3}.
```

O seno hiperbólico é $\sinh x=(e^x-e^{-x})/2$, e $\cosh x=(e^x+e^{-x})/2$. As derivadas são $(\sinh x)'=\cosh x$ e $(\cosh x)'=\sinh x$.

O quociente inicial dá $0/0$. A primeira aplicação de L’Hôpital conduz a:

```math
\lim_{x\to0}\frac{\cosh x-\cos x}{3x^2},
```

que ainda dá $0/0$. A segunda aplicação conduz a:

```math
\lim_{x\to0}\frac{\sinh x+\sin x}{6x},
```

novamente com $0/0$. A terceira dá:

```math
\lim_{x\to0}\frac{\cosh x+\cos x}{6}
=\frac{1+1}{6}=\frac13.
```

As funções envolvidas são deriváveis perto de zero, e as derivadas sucessivas dos denominadores, $3x^2$, $6x$ e $6$, são não nulas para $x\ne0$ próximo de zero. O último limite existe, justificando as aplicações anteriores. A derivada de $-\cos x$ é $+\sin x$.

## 3. Limites laterais — 3.9(b) e 3.10(b,c)

Quando o domínio permite a aproximação pelos dois lados, um limite bilateral com valor real $L$ existe se os dois limites laterais são iguais a $L$. É aos **limites laterais** que nos referimos quando comparamos os lados; o bilateral é o limite sem o sinal $+$ ou $-$.

### 3.9(b)

```math
g(x)=\begin{cases}
\dfrac1x,&x<0,\\
x,&x\geq0.
\end{cases}
```

O aluno apresentou corretamente:

```math
\lim_{x\to0^-}g(x)=-\infty,
\qquad
\lim_{x\to0^+}g(x)=0.
```

Os limites laterais são diferentes, portanto o limite bilateral em zero não existe. Pela esquerda, $x$ é negativo e tem módulo cada vez menor; por isso $1/x$ é negativo e cresce em módulo. Não se trata de efetuar uma divisão por zero.

### 3.10(b)

```math
f(x)=\begin{cases}
x+1,&x<0,\\
2,&x\geq0.
\end{cases}
```

Os limites laterais em zero são, respetivamente, $1$ e $2$. Portanto, o limite bilateral não existe. Esta alínea foi mencionada brevemente; não houve uma resolução detalhada do aluno registada.

### 3.10(c)

```math
f(x)=\begin{cases}
\dfrac1{x^2},&x<0,\\
3x,&x\geq0.
\end{cases}
```

O aluno apresentou corretamente:

```math
\lim_{x\to0^-}f(x)=+\infty,
\qquad
\lim_{x\to0^+}f(x)=0.
```

Mesmo para $x<0$, temos $x^2>0$. Logo, pela esquerda, $1/x^2$ é positivo e cresce sem limite. Os limites laterais diferentes impedem o limite bilateral.

## 4. Ficha 3.10(a) — inexistência do limite de seno de um sobre x

A função é $f(x)=\sin(1/x)$, definida para $x\ne0$.

### Por que a primeira tentativa com o confronto não decide

A desigualdade

```math
-1\leq\sin(1/x)\leq1
```

está correta. Porém, os extremos tendem a valores diferentes. O teorema do confronto garante um limite quando os extremos tendem ao mesmo valor; quando isso não acontece, o enquadramento pode ser inconclusivo.

Por exemplo, também temos $-1\leq0\leq1$, mas a função constante zero tem limite zero. As barreiras $-1$ e $1$ da desigualdade não são os limites laterais da função: elas restringem os valores da função, enquanto os lados da aproximação descrevem os valores de $x$.

### Construir as sucessões a partir do resultado pretendido

Para provar que não há um único limite em zero, procuramos duas maneiras de aproximar $x$ de zero que produzam resultados diferentes para a função. A periodicidade dá valores exatos:

```math
\sin\left(\frac\pi2+2n\pi\right)=1,
\qquad
\sin\left(\frac{3\pi}2+2n\pi\right)=-1.
```

Começamos por escolher o **ângulo** que queremos dentro do seno. Para $n=1,2,3,\ldots$, escolhemos $x_n$ de modo que:

```math
\frac1{x_n}=\frac\pi2+2n\pi
=\frac{\pi+4n\pi}{2}.
```

Só depois isolamos $x_n$:

```math
x_n=\frac1{\frac\pi2+2n\pi}
=\frac2{\pi+4n\pi}\longrightarrow0^+.
```

Ao eliminar a fração interna, o fator $2$ multiplica **todos** os termos do denominador. É por isso que aparece $4n\pi$.

Na substituição, é necessário manter o inverso que já fazia parte da função:

```math
f(x_n)
=\sin\left(\frac1{x_n}\right)
=\sin\left(\frac1{\displaystyle\frac1{\frac\pi2+2n\pi}}\right)
=\sin\left(\frac\pi2+2n\pi\right)=1.
```

Escrever apenas $\sin(1/(\pi/2+2n\pi))$ seria calcular $\sin(x_n)$, e não $f(x_n)=\sin(1/x_n)$.

Para a segunda escolha:

```math
\frac1{y_n}=\frac{3\pi}2+2n\pi
\quad\Longrightarrow\quad
y_n=\frac1{\frac{3\pi}2+2n\pi}
=\frac2{3\pi+4n\pi}\longrightarrow0^+,
```

e

```math
f(y_n)=\sin\left(\frac{3\pi}2+2n\pi\right)=-1.
```

### Distinguir o índice, a entrada, o ângulo e a imagem

| Quantidade | Na primeira escolha, quando $n\to+\infty$ |
| --- | --- |
| $n$, índice da sucessão | Cresce sem limite. |
| $x_n$, entrada da função | Aproxima-se de $0$ por valores positivos. |
| $1/x_n$, ângulo dentro do seno | Cresce para $+\infty$. |
| $f(x_n)$, resultado da função | É sempre $1$. |

Escrever $n\to+\infty$ não significa que o resultado do limite seja infinito. Por exemplo, $\lim_{n\to+\infty}1/n=0$.

A periodicidade do seno vale para um número inteiro de voltas. Podemos escolher apenas voltas positivas, pois os naturais são inteiros. Se usássemos $k\in\mathbb Z$, precisaríamos de indicar a direção: $k\to+\infty$ daria $x_k\to0^+$, enquanto $k\to-\infty$ daria $x_k\to0^-$. Para as duas sucessões desta prova, $n=1,2,3,\ldots$ basta.

### Conclusão pelo critério das sucessões

Se um limite de função em $a$ existe, todas as sucessões de pontos do domínio, diferentes de $a$ e a tender para $a$, devem produzir o mesmo limite para as imagens. Aqui:

```math
\lim_{n\to+\infty}x_n=
\lim_{n\to+\infty}y_n=0,
\qquad
\lim_{n\to+\infty}f(x_n)=1,
\qquad
\lim_{n\to+\infty}f(y_n)=-1.
```

Logo, $\lim_{x\to0}\sin(1/x)$ não existe. As duas sucessões aproximam-se pela direita, pelo que nem o limite lateral direito existe. Não estamos a afirmar que o limite direito seja $1$ e o esquerdo seja $-1$.

**Duas sucessões com imagens de limites diferentes refutam a existência do limite. Duas sucessões com imagens do mesmo limite não bastam para provar a existência:** podem existir outras aproximações com outro comportamento. Para provar a existência pelo critério, o argumento deve abranger qualquer sucessão admissível.

## 5. Ficha 3.11 — formar limites notáveis

### b) Seno de kx dividido por x

```math
\lim_{x\to0}\frac{\sin(kx)}x,
\qquad k\in\mathbb R.
```

Nesta alínea, $k$ é uma constante real. Para $k\ne0$, criamos no denominador o mesmo argumento que aparece no seno:

```math
\frac{\sin(kx)}x
=\frac{k\sin(kx)}{kx}
=k\frac{\sin(kx)}{kx}.
```

Como $kx\to0$, o limite é $k\cdot1=k$. Se $k=0$, a expressão é $0$ para $x\ne0$, e o resultado continua a ser $k=0$. O caso zero deve ser separado porque não podemos multiplicar por $k/k$ quando $k=0$.

L’Hôpital também dá o resultado: a derivada do numerador é $k\cos(kx)$, pela regra da cadeia, e a do denominador é $1$. Assim, o limite é $k\cos0=k$. O aluno identificou a confusão inicial com a regra de derivação de um quociente e voltou a calcular o resultado.

### d) Seno composto com seno

```math
\lim_{x\to0}\frac{\sin(\sin x)}x.
```

O argumento do seno exterior é $\sin x$. Queremos que o denominador do primeiro quociente também seja $\sin x$:

```math
\frac{\sin(\sin x)}x
=\frac{\sin(\sin x)}{\sin x}\frac{\sin x}{x}.
```

A igualdade vale para $x\ne0$ suficientemente próximo de zero, onde $\sin x\ne0$. No primeiro fator, tomar $u=\sin x$ dá $u\to0$ e o limite notável $\sin u/u\to1$. O segundo fator também tende a $1$. Logo, o limite é $1$.

A mudança $y=\sin x$, com $x=\arcsin y$, é válida perto de zero, onde seno e arco seno são inversos. Mas aplicá-la à expressão toda produz $\sin y/\arcsin y$, o que não simplifica de imediato. A fatorização acima usa a substituição apenas onde ela é útil.

O aluno apresentou uma resolução correta por L’Hôpital: a derivada do numerador é $\cos(\sin x)\cos x$, cujo limite é $1$. A fatorização por limites notáveis foi explicada depois.

### f) Arco seno dividido por x

```math
\lim_{x\to0}\frac{\arcsin x}{x}.
```

Tomar $y=\arcsin x$ implica $x=\sin y$ e $y\to0$. Usamos a inversa principal, que assume valores em $[-\pi/2,\pi/2]$; perto de zero, a substituição representa a aproximação original. Para $x\ne0$, também $y\ne0$:

```math
\frac{\arcsin x}{x}
=\frac{y}{\sin y}
=\frac1{\sin y/y}\longrightarrow1.
```

O denominador do último quociente tende a $1\ne0$, justificando a passagem ao recíproco. O aluno apresentou esta resolução.

### g) Arco tangente dividido por seno de 3x

```math
\lim_{x\to0}\frac{\arctan x}{\sin(3x)}.
```

Dividir numerador e denominador por $3x$, para $x\ne0$ próximo de zero, permite escrever:

```math
\frac{\arctan x}{\sin(3x)}
=\frac{\arctan x/(3x)}{\sin(3x)/(3x)}.
```

O denominador tende a $1$. Para o numerador, tomar $y=\arctan x$, pelo que $x=\tan y$ e $y\to0$:

```math
\frac{\arctan x}{3x}
=\frac{y}{3\tan y}
=\frac13\frac{y\cos y}{\sin y}
=\frac13\frac{\cos y}{\sin y/y}
\longrightarrow\frac13.
```

A tangente e o arco tangente são inversos no intervalo $(-\pi/2,\pi/2)$. Perto de zero, os denominadores usados não se anulam fora do ponto. Concluímos que o limite original é $1/3$. O aluno apresentou este método; a operação com $3x$ é divisão, não subtração.

### h) Conjugado junto de pi sobre dois

```math
\lim_{x\to(\pi/2)^-}
\left(\sqrt{1+\tan x}-\sqrt{\tan x}\right).
```

Perto de $\pi/2$ pela esquerda, $\tan x>0$ e $\tan x\to+\infty$. As raízes estão definidas e temos uma diferença do tipo $\infty-\infty$. Racionalizando:

```math
\sqrt{1+\tan x}-\sqrt{\tan x}
=\frac{(1+\tan x)-\tan x}
{\sqrt{1+\tan x}+\sqrt{\tan x}}
=\frac1{\sqrt{1+\tan x}+\sqrt{\tan x}}
\longrightarrow0.
```

O aluno corrigiu o sinal da tendência da tangente e apresentou a racionalização.

### i) Tangente de um sobre x no infinito

```math
\lim_{x\to+\infty}2x\tan(1/x).
```

A mudança adequada é:

```math
u=\frac1x,
\qquad x=\frac1u,
\qquad x\to+\infty\Rightarrow u\to0^+.
```

Substituímos tanto o fator $x$ exterior como o argumento $1/x$:

```math
2x\tan(1/x)
=2\frac1u\tan u
=2\frac{\tan u}{u}
=2\frac{\sin u}{u}\frac1{\cos u}
\longrightarrow2\cdot1\cdot1=2.
```

O aluno tentou reutilizar sucessões como $x_n=1/(\pi/4+n\pi)$ e $y_n=1/(3\pi/4+n\pi)$. Estas tendem a zero, não a $+\infty$, e por isso estudam outro ponto. As imagens dessas escolhas tendem ambas a zero, mas isso também não provaria, por si só, um limite da função em zero. O resultado pedido, corrigido com ajuda, é $2$.

## 6. Estado do estudo e ligações com a continuidade

| Exercício | Evidência registada |
| --- | --- |
| 3.8(o,p) | Resultados do aluno confirmados no histórico; explicações registadas, sem uma tentativa completa apresentada nesse histórico. |
| 3.8(q) | Tentativa com conjugado apresentada; erro no numerador corrigido para $-5$ e limite confirmado como $0$. |
| 3.8(r) | Demonstração por L’Hôpital apresentada; execução autónoma ainda não verificada. |
| 3.9(b), 3.10(c) | Cálculos dos limites laterais apresentados corretamente pelo aluno. |
| 3.10(a) | Resolvido com ajuda; o aluno reconstruiu a escolha das sucessões. A notação dos limites voltou a precisar de esclarecimento posteriormente. |
| 3.10(b) | Resultado mencionado; sem resolução detalhada do aluno. |
| 3.11(b,d) | L’Hôpital discutido e resultados obtidos pelo aluno; métodos com limites notáveis explicados com ajuda. |
| 3.11(f,g,h) | Métodos apresentados pelo aluno e conferidos, com ajustes de escrita e sinal. |
| 3.11(i) | Tentativa por sucessões analisada; ponto da aproximação e conclusão corrigidos com ajuda. |

O limite notável de 3.11(a) foi utilizado como ferramenta. As alíneas 3.11(c,e) não têm resolução discutida registada nestas sessões.

O contraste com $x^2\sin(1/x)-2x$ na alínea 3.12(i) é desenvolvido em [Continuidade e prolongamento](continuidade-e-prolongamento.md): o seno oscila, mas o fator $x^2$ faz a amplitude da sua contribuição tender a zero. O aluno aplicou depois o confronto à função inteira. Os exercícios antigos R1–R3 e as pendências de revisão mantêm o estado indicado em [PROGRESSO.md](../PROGRESSO.md).
