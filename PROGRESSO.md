# Progresso de estudo — Análise Matemática I

Última atualização: **24 de outubro de 2026**.

## Onde parámos

**3.13(a): interpretação de prolongamento por continuidade à origem**, aplicado à função de 3.12(e):

```math
f(x)=\frac1{1-e^{1/x}}.
```

O aluno relacionou o pedido com escolher uma constante num ramo. Foi explicado que se procura um valor real para a função em zero que coincida com os dois limites laterais. **Os limites laterais desta função e a conclusão sobre a existência do prolongamento ainda não foram calculados na conversa.** Retomar pela tentativa do aluno.

A próxima sessão está prevista pelo aluno para **25 de outubro de 2026**. É uma indicação de continuidade do estudo, não uma atualização automática: o GitHub só volta a ser atualizado quando o aluno pedir.

## Materiais e notas

- [Ficha de exercícios original](materiais/Ficha_exercicios.pdf), recebida nesta conversa e guardada para próximas sessões.
- [Limites e radicais](notas/limites-e-radicais.md): material anterior preservado; enunciados de 3.8(c), (d) e (j) agora confirmados.
- [Limites trigonométricos, laterais e sucessões](notas/limites-trigonometricos-e-sucessoes.md): 3.8(o–r), 3.9(b), 3.10 e alíneas discutidas de 3.11.
- [Continuidade e prolongamento](notas/continuidade-e-prolongamento.md): alíneas discutidas de 3.12 e interpretação de 3.13(a).

As alíneas confirmadas na ficha não são automaticamente consideradas resolvidas. As notas são um registo das sessões, não um solucionário completo.

## Evidências das sessões de 20 e 24 de outubro

| Exercícios | Estado e evidência observada |
| --- | --- |
| 3.8(o,p) | Resultados 1 e 1 apresentados no histórico e confirmados; não há desenvolvimento completo do aluno recuperado. |
| 3.8(q) | Tentativa com conjugado apresentada; numerador corrigido de 1 para −5 e limite 0 explicado. Resolvido com ajuda. |
| 3.8(r) | Resolução por três aplicações de L’Hôpital apresentada no histórico, com resultado 1/3. Visto; execução autónoma não verificada. |
| 3.9(b), 3.10(c) | Laterais calculados corretamente pelo aluno; corrigida a distinção de linguagem entre limites laterais e bilateral. |
| 3.10(a) | Prova por sucessões construída com ajuda substancial. Depois o aluno reconstruiu a escolha dos ângulos, as inversões e a conclusão; a notação voltou a gerar dúvidas em 3.12(i). |
| 3.10(b) | Resultado comentado brevemente, sem resolução detalhada do aluno. |
| 3.11(b) | Identificada pelo aluno a confusão entre L’Hôpital e a derivada de um quociente; relatou o resultado k depois da correção. Método pelo limite notável demonstrado com ajuda. |
| 3.11(d) | O aluno apresentou corretamente a derivação por L’Hôpital e o resultado 1. A fatorização em dois limites notáveis foi explicada. |
| 3.11(f,g,h) | Tentativas próprias apresentadas e conferidas: resultados 1, 1/3 e 0. Ajustada a escrita em (g); o aluno corrigiu o sinal da tendência da tangente em (h). |
| 3.11(i) | Tentativa com sucessões tendentes ao ponto errado e conclusão por dois exemplos iguais corrigidas. Solução por mudança de variável apresentada, com resultado 2; nova tentativa autónoma ainda não vista. |
| 3.12(a) | Domínio e lateral direito corretos; esclarecida a distinção entre continuidade no domínio e prolongamento a zero. |
| 3.12(b,c,f) | Domínios e justificações apresentados pelo aluno e conferidos. O valor absoluto em (f), omitido na transcrição do assistente, foi reposto após inspeção visual da ficha; as conclusões mantêm-se. |
| 3.12(d) | Condição do logaritmo identificada; exclusão dos múltiplos de pi obtida com ajuda, corrigindo a desigualdade proposta. |
| 3.12(g) | Fatorização e critério corretos; o aluno reconsiderou o domínio. Limite corrigido para 8, diferente de f(4)=1. |
| 3.12(h) | Laterais e valor no ponto calculados como −a; domínio corrigido para todos os reais por respeitar as condições de cada ramo. |
| 3.12(i) | Depois da explicação do confronto, o aluno apresentou uma prova correta usando a função inteira entre −x²−2x e x²−2x. Reconstruído com ajuda; transferência para um exercício novo ainda por observar. |
| 3.13(a) | Apenas interpretação do enunciado e da escolha de uma constante. A tentativa dos laterais permanece pendente. |

Estes estados descrevem o que foi observado, sem transformar uma explicação compreendida ou repetida numa declaração de domínio autónomo.

## Dúvidas e métodos a consolidar

- **Construção de sucessões:** começar pelo ângulo desejado, isolar o termo da sucessão e substituir a expressão completa na função, mantendo todos os inversos.
- **Três tendências diferentes:** o índice n tende a infinito; os termos x_n podem tender a zero; as imagens f(x_n) têm o seu próprio comportamento. Os limites das imagens escrevem-se com n a tender a infinito.
- **Critério de sucessões:** dois limites diferentes nas imagens refutam um limite de função; dois iguais não provam a existência. Para provar existência, o argumento deve abranger qualquer sucessão admissível.
- **Confronto:** extremos com limites diferentes são inconclusivos. O fator x² reduz a oscilação de sin(1/x), permitindo provar o limite de x² sin(1/x) − 2x.
- **Limites notáveis:** fazer coincidir o argumento do seno com o denominador e verificar que esse argumento tende a zero. Com u=1/x, a nova aproximação depende da aproximação original.
- **L’Hôpital:** derivar numerador e denominador separadamente, sob as hipóteses da regra; não usar a fórmula da derivada do quociente. Preferir uma justificação direta por limite notável ou confronto quando o aluno a pedir.
- **Domínio e continuidade:** uma função pode ser contínua em todo o seu domínio e não estar definida num ponto excluído. Num ramo, só contam as restrições da expressão na região onde esse ramo é usado.
- **Junções:** justificar a continuidade no interior de cada região pelas operações e verificar separadamente a igualdade dos limites pertinentes com o valor no ponto.
- **Prolongamento:** acrescentar um valor no ponto excluído; só há prolongamento contínuo real quando o limite nesse ponto existe e é finito.

## Material anterior preservado

A transcrição de 19 de outubro registava uso do MMC 12 para raízes de índices 3 e 4, perguntas sobre substituir na expressão simplificada e um exemplo com índices 5 e 3 em que foi reconhecido o MMC 15 e obtido 3/5 com esclarecimentos sobre fatorização. Também foi identificada corretamente a raiz sexta de 64 como 2.

Os apontamentos mantêm as explicações sobre diferenças de potências, cancelamento fora do ponto, mudanças de variável e confronto no infinito. A ficha agora confirma que o exemplo de índices 3 e 4 corresponde a 3.8(d). O exemplo de índices 5 e 3 continua identificado como análogo; não corresponde a 3.8(j).

## Pendências

- [ ] Tentar os dois limites laterais de 3.12(e) e concluir o 3.13(a).
- [ ] Avançar para 3.13(b) e outros exercícios que o aluno escolher.
- [ ] Rever a notação dos limites de sucessões numa oportunidade pertinente, sem repetir toda a explicação se a tentativa já mostrar compreensão.
- [ ] 3.11(c,e): sem resolução discutida registada; não considerar concluídas.
- [ ] 3.8(c,j): enunciados confirmados, mas sem tentativa verificável recuperada; resolver ou conferir quando o aluno os retomar.
- [ ] R1 — conjugado e cancelamento, no final dos apontamentos de radicais.
- [ ] R2 — MMC de índices e fatorização.
- [ ] R3 — confronto no infinito e mudança de variável com sinal.
- [ ] Incorporar critérios de justificação do docente se forem fornecidos.

R1–R3 continuam sem soluções publicadas e sem tentativa registada. Não foram substituídos pelos exercícios da ficha.

## Preferências atualizadas

- Desde 24 de outubro: notação internacional em LaTeX, com $\sin$, $\tan$, $\arcsin$ e $\arctan$, no chat e nas notas.
- Explicar a origem de uma escolha antes da fórmula geral. Quando houver confusão, reduzir a explicação a uma ideia de cada vez e mostrar inversões e substituições explicitamente.
- Preservadas as orientações de compreensão pelos fundamentos adicionadas ao repositório em 22 de outubro.

## Verificação desta atualização — 24 de outubro de 2026

- Conferidos os enunciados no PDF, incluindo inspeção visual das páginas numeradas 5 e 6.
- Corrigidas as correspondências antigas de 3.8 e o valor absoluto de 3.12(f).
- Validadas localmente 102 fórmulas em destaque e 416 expressões inline com KaTeX, além dos 28 links internos. Conferida a preservação das barras invertidas e dos blocos math.
- Inspecionada a apresentação local da matriz de duas linhas, da substituição com inversos encaixados, dos ramos e do confronto. Esta conferência local não equivale à aba Preview do GitHub.
- A pré-visualização privada do GitHub não está acessível pelo navegador deste ambiente (resposta 404). A leitura pela ligação autorizada ao GitHub permite verificar o conteúdo, mas não equivale a uma conferência visual dessa apresentação.

## Verificação da apresentação — 19 de outubro de 2026

- Confirmado o envio dos cinco ficheiros e a correspondência entre o conteúdo preparado e o guardado no GitHub.
- Conferida a aba Preview no GitHub: a matriz de exemplo aparece com duas linhas, e a soma com expoentes e as expressões com raízes renderizam.
- Conferidas as fatorizações dos exemplos com índices 3 e 4 e com índices 5 e 3.
- Mantida a notação matemática correta, incluindo as duas barras entre linhas da matriz, sem alterar fórmulas por pequenas diferenças visuais no tamanho dos parênteses.
