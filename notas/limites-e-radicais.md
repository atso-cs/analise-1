# Análise Matemática I — Limites e radicais

Apontamentos de estudo — 19 de outubro de 2026.

[Índice](../README.md) · [Progresso e pendências](../PROGRESSO.md)

## Origem e estado

Base: conversa «Resolver limite com radicais», referente à ficha 3.8. A recuperação disponível inclui transcrições incompletas e respostas antigas sem conteúdo legível. Por isso, as expressões reconstruídas abaixo estão identificadas como exemplos compatíveis, sem lhes atribuir uma alínea não confirmada.

| Alínea pedida | Estado |
| --- | --- |
| j), d), c) | Enunciados completos e correspondência com os exemplos por confirmar na ficha original. |
| l) | A transcrição associa esta alínea a $\lim_{x\to+\infty}\mathrm{sen}(x)/x$. Resolvida abaixo. |

Não constitui uma transcrição integral das soluções originais.

## Ideia e notação

Um limite descreve o comportamento de uma função quando a variável se aproxima de um ponto, mesmo que a função não esteja definida nesse ponto. Escrever $\lim_{x\to a}f(x)=L$ significa que podemos tornar $f(x)$ tão próximo de $L$ quanto quisermos tomando $x$ suficientemente próximo de $a$, com $x\ne a$ e dentro do domínio.

A notação $x\to a^+$ indica aproximação por valores maiores que $a$; $x\to a^-$, por valores menores. Quando há pontos do domínio dos dois lados, o limite bilateral existe com valor $L$ se ambos os limites laterais existem e são iguais a $L$.

Em $x\to+\infty$, consideramos valores positivos cada vez maiores; em $x\to-\infty$, valores negativos com módulo cada vez maior. O infinito não é um número para substituir numa expressão.

## 1. Antes de transformar um limite

1. Verificar o domínio e de que lado se pode aproximar o ponto.
2. Tentar substituir, quando as funções envolvidas são contínuas e o denominador não se anula.
3. Se aparecer $0/0$, procurar uma transformação: fatorização, conjugado ou mudança de variável.
4. Cancelar apenas fatores comuns não nulos para os valores considerados.
5. Substituir na expressão simplificada se esta for contínua no ponto e tiver denominador não nulo.

$0/0$ é uma **indeterminação**, não um número nem a resposta. Por exemplo, quando $x\to0$, $x/x\to1$, $x^2/x\to0$ e $x/x^2=1/x$ não tem limite bilateral finito.

O limite depende dos valores próximos do ponto. A igualdade

```math
\frac{(x-a)g(x)}{(x-a)h(x)}=\frac{g(x)}{h(x)}
```

vale onde $x\ne a$ e os denominadores não são zero; isso basta para calcular o limite, mesmo que a expressão inicial não esteja definida em $a$.

## 2. Conjugados e diferenças de quadrados

```math
(A-B)(A+B)=A^2-B^2.
```

Para eliminar uma diferença de raízes quadradas, multiplicar numerador e denominador pelo conjugado, desde que ele não seja zero na vizinhança considerada.

**Exemplo análogo resolvido:**

```math
\lim_{x\to4}\frac{\sqrt{x}-2}{x-4}.
```

O domínio exige $x\ge0$ e $x\ne4$. A substituição dá $0/0$. Para $x\ne4$ próximo de 4:

```math
\frac{\sqrt{x}-2}{x-4}\frac{\sqrt{x}+2}{\sqrt{x}+2}
=\frac{x-4}{(x-4)(\sqrt{x}+2)}
=\frac1{\sqrt{x}+2}.
```

Agora o denominador tende a $4\ne0$, logo o limite é $1/4$.

O objetivo do conjugado é produzir um fator que se possa cancelar. Não se cancelam parcelas de uma soma: em $(x+1)/(x+2)$ não se pode «cortar o x».

## 3. Cubos e diferença geral de potências

```math
a^3-b^3=(a-b)(a^2+ab+b^2).
```

Para um inteiro $n\ge1$:

```math
a^n-b^n=(a-b)\sum_{k=0}^{n-1}a^{n-1-k}b^k.
```

Ou seja, os expoentes de $a$ descem e os de $b$ sobem; cada termo tem grau total $n-1$. Ao distribuir, os termos intermédios cancelam, restando $a^n-b^n$. É uma identidade algébrica; não exige $a\ne b$. Essa condição surge quando se divide por $a-b$.

Se $b=1$, fica:

```math
a^n-1=(a-1)(a^{n-1}+a^{n-2}+\cdots+a+1).
```

**Correção da dúvida sobre constantes:**

```math
a^6-64=a^6-2^6=(a-2)(a^5+2a^4+4a^3+8a^2+16a+32).
```

Já $a^5-9$ não tem fator $a-3$: em $a=3$ vale $243-9=234$. Para usar a fórmula com expoente 5, escrever $9=b^5$, isto é, $b=\sqrt[5]{9}$. Os coeficientes serão $1,b,b^2,b^3,b^4$.

Por outro lado, $a^4-9=(a^2-3)(a^2+3)$ é diretamente uma diferença de quadrados. A identidade escolhida depende das potências presentes, não apenas do número subtraído.

### Exemplo análogo resolvido: diferença de cubos

Calcular $\lim_{x\to8}(\sqrt[3]{x}-2)/(x-8)$. A substituição direta dá $0/0$. Tomar $t=\sqrt[3]{x}$; então $x=t^3$ e $t\to2$. A raiz cúbica é contínua e esta mudança tem inversa $x=t^3$, por isso representa a aproximação original.

```math
\frac{\sqrt[3]{x}-2}{x-8}
=\frac{t-2}{t^3-2^3}
=\frac{t-2}{(t-2)(t^2+2t+4)}
=\frac1{t^2+2t+4},
\qquad t\ne2.
```

O denominador restante tende a $4+4+4=12$, logo o limite é $1/12$. A soma $t^2+2t+4=(t+1)^2+3$ é sempre positiva. Para uma raiz cúbica, este produto elimina o radical usando a diferença de cubos; o conjugado de duas parcelas foi útil no exemplo da raiz quadrada.

## 4. Raízes: mudança de variável e MMC dos índices

Para raízes de índices $p$ e $q$ de uma mesma variável positiva, escolher $m=\mathrm{mmc}(p,q)$ e $t=\sqrt[m]{x}$, portanto $x=t^m$. Então $\sqrt[p]{x}=t^{m/p}$ e $\sqrt[q]{x}=t^{m/q}$. Perto de $x=1$, temos $t\to1$. Se aparecerem raízes pares, respeitar o domínio e a raiz principal não negativa. Fora desta situação, verificar os sinais antes de aplicar o procedimento.

### Exemplo compatível com a transcrição: índices 3 e 4

```math
\lim_{x\to1}\frac{\sqrt[3]{x}-1}{\sqrt[4]{x}-1}.
```

Como $\mathrm{mmc}(3,4)=12$, tomar $t=\sqrt[12]{x}$, com $x>0$ próximo de 1. Assim $x=t^{12}$ e $t\to1$:

```math
\lim_{t\to1}\frac{t^4-1}{t^3-1}
=\lim_{t\to1}\frac{(t-1)(t+1)(t^2+1)}{(t-1)(t^2+t+1)}.
```

Para $t\ne1$, cancelar $t-1$. O denominador restante tende a 3, pelo que:

```math
\frac{(1+1)(1+1)}{1+1+1}=\frac43.
```

Não é necessário voltar a $x$: o limite já foi calculado na nova variável. Para regressar à variável original, seria preciso usar $t=x^{1/12}$. Renomear uma variável muda apenas a letra; não desfaz a substituição.

### Exemplo compatível com a transcrição: índices 5 e 3

```math
\lim_{x\to1}\frac{\sqrt[5]{x}-1}{\sqrt[3]{x}-1}.
```

Tomar $t=\sqrt[15]{x}$, pois $\mathrm{mmc}(5,3)=15$. Então:

```math
\lim_{t\to1}\frac{t^3-1}{t^5-1}
=\lim_{t\to1}\frac{(t-1)(t^2+t+1)}{(t-1)(t^4+t^3+t^2+t+1)}
=\frac35.
```

O cancelamento vale para $t\ne1$; depois o denominador tende a $5\ne0$. Não é preciso usar Ruffini: a diferença de potências já fornece a fatorização. Também não há motivo para continuar a transformar uma fração cuja substituição já é válida.

## 5. Mudanças de variável e limites laterais

| Aproximação original | Substituição | Nova aproximação |
| --- | --- | --- |
| $x\to+\infty$ | $y=1/x$ | $y\to0^+$ |
| $x\to-\infty$ | $y=1/x$ | $y\to0^-$ |
| $y\to0^-$ | $u=-y$ | $u\to0^+$ |
| $y\to0^+$ | $u=-y$ | $u\to0^-$ |
| $y\to0^+$ | $u=1/y$ | $u\to+\infty$ |
| $y\to0^-$ | $u=1/y$ | $u\to-\infty$ |

Em particular, $1/(-1\,000\,000)=-10^{-6}=-0{,}000001$. São valores negativos cada vez mais próximos de zero quando $x\to-\infty$.

Não se substitui $y=0$ em $1/y$: a expressão não está definida aí. A notação de limite descreve aproximação, não permite dividir por zero. Se a trajetória é unilateral, conservá-la na mudança de variável; um limite bilateral conhecido pode depois justificar o mesmo valor para esse lado.

**Exemplo exponencial mencionado:**

```math
\lim_{y\to0^-}\frac{e^{-y}-1}{-y}.
```

Com $u=-y$, temos $y=-u$ e $u\to0^+$. Logo:

```math
\lim_{u\to0^+}\frac{e^u-1}{u}=1,
```

pelo limite notável $\lim_{u\to0}(e^u-1)/u=1$. A substituição é $y=-u$, não $y=-1$.

## 6. Alínea l): seno dividido por x no infinito

Queremos calcular $\lim_{x\to+\infty}\mathrm{sen}(x)/x$.

O seno oscila, mas permanece entre -1 e 1. Como $x>0$ para valores suficientemente grandes:

```math
-\frac1x\le\frac{\mathrm{sen} x}{x}\le\frac1x.
```

Os dois extremos tendem a zero. Pelo **teorema do confronto**, o limite é **0**.

Também se pode usar $y=1/x$: $y\to0^+$ e a expressão passa a $y\mathrm{sen}(1/y)$. Como $|y\mathrm{sen}(1/y)|\le |y|\to0$, obtém-se o mesmo resultado.

Não aplicar aqui o limite notável $\mathrm{sen} u/u\to1$, que exige $u\to0$ (ângulos em radianos). Se $u=1/y$ e $y\to0^+$, então $u\to+\infty$; essa segunda substituição regressa ao problema inicial. Também não se justifica a resposta por «$\mathrm{sen}(+\infty)$»: o seno não tem limite no infinito.

Para uma resposta escrita, indicar a desigualdade e o teorema dá uma justificação completa. A exigência concreta de uma frequência depende dos critérios do docente, que não foram fornecidos.

## 7. Dúvidas esclarecidas e erros a evitar

- A fórmula $a^n-1$ é um caso particular de $a^n-b^n$, não apenas uma diferença de quadrados.
- A constante deve ser escrita com o mesmo expoente: em $a^n-C$, usar $b^n=C$, quando existir a raiz real adequada.
- Cancelar fatores comuns é válido fora do ponto; não é necessário que a expressão inicial esteja definida no ponto do limite.
- Depois de remover a indeterminação, substituir quando as condições de continuidade e denominador não nulo estiverem satisfeitas.
- O MMC é dos índices: $12/3=4$, $12/4=3$, $15/5=3$, $15/3=5$.
- Uma mudança de variável deve registar a nova tendência e respeitar o domínio e o lado da aproximação.
- Uma função limitada vezes uma função que tende a zero tende a zero; isto explica o exemplo do seno no infinito.

Estes pontos foram esclarecidos nos apontamentos; a autonomia do aluno deve ser confirmada com exercícios novos.

## 8. Exercícios de revisão — para tentares

Estes exercícios são análogos, não enunciados confirmados da ficha 3.8. Apresenta os passos e justifica as operações. As soluções ficam para depois da tua tentativa.

### R1 — Conjugado

Calcula:

```math
\lim_{x\to9}\frac{\sqrt{x}-3}{x-9}.
```

Indica o domínio da expressão e explica por que podes cancelar um fator que se anula em $x=9$.

### R2 — Raízes de índices diferentes

Calcula:

```math
\lim_{x\to1}\frac{\sqrt[4]{x}-1}{\sqrt[6]{x}-1}.
```

Escolhe uma mudança de variável com o MMC dos índices. Regista a nova tendência e justifica a substituição final.

### R3 — Confronto e sinais

Calcula:

```math
\lim_{x\to-\infty}\frac{\cos(3x)}x.
```

Usa uma estimativa com valor absoluto. Depois verifica a tendência de $y=1/x$ e de $u=-y$, e explica por que um limite notável no zero não se aplica diretamente à expressão original.

## 9. Progresso e próximos passos

As estratégias e correções estão registadas acima. A compreensão autónoma será confirmada pelas tuas resoluções, sem presumir que uma explicação lida já foi dominada.

Falta consultar a ficha 3.8 para confirmar os enunciados de j), d) e c), associar os exemplos às alíneas e completar o que faltar. O registo atualizado de onde parámos, das dúvidas e dos exercícios pendentes encontra-se em [PROGRESSO.md](../PROGRESSO.md).
