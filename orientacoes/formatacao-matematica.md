# Formatação matemática para o GitHub

Preferências registadas em 19 de outubro de 2026, a partir da experiência do aluno com o repositório de Álgebra Linear.

## Regras

1. Guardar as notas em Markdown com fórmulas em LaTeX, corretas e reutilizáveis.
2. Usar blocos cercados com a linguagem `math` para equações em destaque e matrizes. Não colocar `$$` dentro desses blocos.
3. Colocar matrizes fora dos parágrafos e preservar `\\` como separador entre linhas. Uma passagem anterior pelo processamento Markdown retirou uma barra e juntou as linhas.
4. Para expressões simples no texto, usar delimitadores de dólar simples, como em $x\ne a$.
5. Na pré-visualização usada anteriormente, o comando `\operatorname` foi rejeitado. Usar `\mathrm{tr}`, `\mathrm{car}`, `\mathrm{adj}` e `\mathrm{mmc}` para esses nomes. Para seno em português, usar `\mathrm{sen}`; não depender de um comando personalizado `\sen`.
6. Conferir a pré-visualização após o primeiro envio, incluindo a matriz abaixo e as fórmulas mais complexas. Ler o Raw confirma a fonte, mas não a apresentação.
7. Manter a notação correta mesmo que o navegador mostre pequenas imperfeições no tamanho dos parênteses. Não alterar fórmulas corretas apenas para perseguir esse detalhe visual.
8. Ao exportar para outro visualizador ou PDF, adaptar os delimitadores ao destino, preservando as fórmulas.
9. Estas regras aplicam-se aos ficheiros do repositório. No chat, apresentar as fórmulas renderizadas normalmente, sem blocos de código ou blocos especiais de escrita.

## Amostras para conferir a apresentação

A matriz é apenas uma amostra de formatação, não uma indicação do conteúdo ou programa de Análise Matemática I.

### Matriz com duas linhas

```math
M=\begin{pmatrix}
1 & 2 \\
3 & 4
\end{pmatrix},
\qquad \mathrm{tr}(M)=5.
```

Na apresentação, a primeira linha deve conter 1 e 2; a segunda, 3 e 4.

### Fórmula com soma e expoentes

```math
a^n-b^n=(a-b)\sum_{k=0}^{n-1}a^{n-1-k}b^k,
\qquad n\in\mathbb{N},\quad n\ge1.
```

### Raízes e resolução em várias linhas

```math
\begin{aligned}
t&=\sqrt[15]{x},\qquad x=t^{15},\qquad x\to1\Rightarrow t\to1,\\
\lim_{x\to1}\frac{\sqrt[5]{x}-1}{\sqrt[3]{x}-1}
&=\lim_{t\to1}\frac{t^3-1}{t^5-1}\\
&=\lim_{t\to1}\frac{t^2+t+1}{t^4+t^3+t^2+t+1}
=\frac35.
\end{aligned}
```

O cancelamento implícito na última passagem é válido para $t\ne1$, numa vizinhança de 1.

### Nomes em letra direita e desigualdade

```math
\mathrm{mmc}(3,5)=15,
\qquad
-\frac1x\le\frac{\mathrm{sen}(x)}x\le\frac1x
\quad (x>0).
```

## Conferência em futuras atualizações

- Verificar as barras invertidas e a estrutura dos blocos na fonte.
- Abrir a aba de apresentação do ficheiro no GitHub.
- Confirmar duas linhas na matriz, frações, índices das raízes, expoentes, soma, limites e nomes em letra direita.
- Se houver uma falha real de apresentação, corrigir a fonte e conferir novamente.
- Registar o que foi efetivamente verificado, sem confundir leitura da fonte com inspeção visual.
