# Continuidade pela definição ε–δ

Sessão de **26 de outubro de 2026**.

[Índice](../README.md) · [Revisão curta](revisao-limites-e-continuidade.md) · [Progresso](../PROGRESSO.md)

Os dois exercícios abaixo foram propostos no chat e trabalhados na sessão. São exemplos de treino, sem numeração atribuída à ficha.

## 1. O que se pretende provar

Uma função $f$ é contínua em $a\in D_f$ quando:

```math
\forall\varepsilon>0\;\exists\delta>0\;\forall x\in D_f:
\quad
|x-a|<\delta
\;\Longrightarrow\;
|f(x)-f(a)|<\varepsilon.
```

- $\varepsilon$ lê-se **épsilon** e limita a distância entre a saída $f(x)$ e a saída $f(a)$.
- $\delta$ lê-se **delta** e limita a distância entre a entrada $x$ e o ponto $a$.
- Para qualquer tolerância positiva nas saídas, escolhemos uma tolerância positiva nas entradas que garanta o pedido.

A ordem importa: recebemos $\varepsilon$, escolhemos $\delta$ e verificamos a implicação para **todos** os $x$ do domínio suficientemente próximos de $a$. A escolha de $\delta$ pode depender de $\varepsilon$, da função e do ponto fixado; não pode variar com o $x$ que depois percorre a vizinhança.

Para um limite geral $\lim_{x\to a}f(x)=L$, a condição correspondente é:

```math
\forall\varepsilon>0\;\exists\delta>0\;\forall x\in D_f:
\quad
0<|x-a|<\delta
\;\Longrightarrow\;
|f(x)-L|<\varepsilon.
```

Aqui considera-se $a$ um ponto de acumulação do domínio. Excluímos $x=a$ e não exigimos que $f(a)$ exista. Na continuidade, o alvo é precisamente $f(a)$ e não precisamos de excluir o próprio ponto.

## 2. Descobrir δ e depois apresentar a prova

Na preparação, começamos por simplificar a distância entre as saídas. Procuramos uma condição sobre $|x-a|$ que seja suficiente para a tornar menor do que $\varepsilon$.

Na versão final:

1. Escrever «Seja $\varepsilon>0$».
2. Escolher explicitamente $\delta>0$.
3. Tomar um $x$ admissível com $|x-a|<\delta$.
4. Mostrar que essa condição implica $|f(x)-f(a)|<\varepsilon$.
5. Concluir a continuidade no ponto.

Não se substitui $|x-a|$ por $\delta$ como se fossem iguais: usamos a desigualdade estrita $|x-a|<\delta$. A escolha de $\delta$ não precisa de ser a maior possível; basta que funcione.

## 3. Exercício 1: f(x)=3x−2 em a=1

Primeiro:

```math
f(1)=1,
\qquad
|f(x)-f(1)|
=|(3x-2)-1|
=|3(x-1)|
=3|x-1|.
```

Para garantir uma distância menor do que $\varepsilon$, basta exigir:

```math
3|x-1|<\varepsilon
\iff |x-1|<\frac{\varepsilon}{3}.
```

Isto sugere $\delta=\varepsilon/3$. É uma escolha positiva que não depende de $x$.

### Redação curta

Seja $\varepsilon>0$. Escolhemos $\delta=\varepsilon/3>0$. Para qualquer $x\in\mathbb R$ tal que $|x-1|<\delta$, temos:

```math
|f(x)-f(1)|=3|x-1|<3\delta=\varepsilon.
```

Logo, $f$ é contínua em 1.

O aluno encontrou corretamente $\delta=\varepsilon/|3|=\varepsilon/3$. Na escrita da condição, é importante manter o módulo de $x-1$.

## 4. Exercício 2: g(x)=x² em a=0

Temos $g(0)=0$ e:

```math
|g(x)-g(0)|=|x^2|=|x|^2.
```

Como $\varepsilon>0$ e $|x|\geq0$:

```math
|x|^2<\varepsilon
\iff |x|<\sqrt{\varepsilon}.
```

Escolhemos, portanto, $\delta=\sqrt{\varepsilon}$.

### Redação curta

Seja $\varepsilon>0$. Escolhemos $\delta=\sqrt{\varepsilon}>0$. Para qualquer $x\in\mathbb R$ tal que $|x|<\delta$, temos:

```math
|g(x)-g(0)|=|x|^2<\delta^2=\varepsilon.
```

Logo, $g$ é contínua em zero.

### Por que a tentativa δ=ε/|x| não serve

O aluno começou corretamente por escrever $|x^2|=|x|\,|x|$, mas propôs depois $\delta=\varepsilon/|x|$.

Essa proposta depende do próprio $x$, quando precisamos de uma única escolha de $\delta$ que funcione para todos os $x$ próximos do ponto. Além disso, a fração não está definida em $x=0$. Tomar a raiz quadrada evita os dois problemas.

A escolha $\sqrt{\varepsilon}$ e a verificação final foram apresentadas com ajuda; ainda não foi registada uma nova execução autónoma desta prova.

## 5. Módulo e sinais

```math
|ab|=|a|\,|b|,
\qquad |3|=|-3|=3,
\qquad |x^2|=|x|^2.
```

A igualdade $|3|=3$ resulta de 3 ser positivo. Não depende das condições $\varepsilon>0$ ou $\delta>0$.

Não se pode substituir $|x|$ por $x$ sem garantir $x\geq0$. Perto de zero, o exercício considera entradas dos dois lados; quando $x<0$, temos $|x|=-x$.

## 6. Igualdade, equivalência, implicação e conclusão

| Símbolo | Uso |
| --- | --- |
| $=$ | Igualdade entre expressões ou valores. |
| $\iff$ | Equivalência entre afirmações: a implicação vale nos dois sentidos. |
| $\Rightarrow$ | Uma afirmação implica a seguinte. |
| $\therefore$ | «Portanto»: introduz uma conclusão. Não é sinal de equivalência. |

Ao resolver equações ou desigualdades, só usamos equivalência quando a transformação preserva as soluções nos dois sentidos, sob as condições indicadas. Dividir por uma expressão exige verificar que ela não é zero.

Na prova final, escrever «Logo» ou «Portanto» é suficiente; o símbolo de três pontos não é obrigatório.
