---
title: Istruzione If...Then...Else (Visual Basic) |
ms.date: 04/16/2018
f1_keywords:
- vb.ElseIf
- vb.Then
- vb.If
- vb.EndIf
helpviewer_keywords:
- ElseIf statement [Visual Basic], If...Then...Else
- Then statement [Visual Basic], If...Then...Else
- control flow [Visual Basic], branching
- execution [Visual Basic], conditional
- TypeOf...Is expression, and If...Then...Else statements
- If...Then...Else statements
- If statement [Visual Basic], If...Then...Else
- If statement [Visual Basic]
- Is operator [Visual Basic], in If...Then...Else statements
- If Operator [Visual Basic]
- branching [Visual Basic], conditional
- If function [Visual Basic], and If...Then...Else statements
- Else statement [Visual Basic]
ms.assetid: 790068a2-1307-4e28-8a72-be5ebda099e9
ms.openlocfilehash: db81a1c41809b563d5f9d0777c3feb064c5e540b
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400703"
---
# <a name="ifthenelse-statement-visual-basic"></a>Istruzione If...Then...Else (Visual Basic) |

Esegue un gruppo di istruzioni in base a determinate condizioni, a seconda del valore di un'espressione.

## <a name="syntax"></a>Sintassi

```vb
' Multiline syntax:
If condition [ Then ]
    [ statements ]
[ ElseIf elseifcondition [ Then ]
    [ elseifstatements ] ]
[ Else
    [ elsestatements ] ]
End If

' Single-line syntax:
If condition Then [ statements ] [ Else [ elsestatements ] ]
```

## <a name="quick-links-to-example-code"></a>Collegamenti rapidi al codice di esempio

Questo articolo include diversi esempi che illustrano gli `If`usi del... `Then`... `Else` istruzione:

- [Esempio di sintassi su più righe](#multi-line)
- [Esempio di sintassi annidata](#nested)
- [Esempio di sintassi a riga singola](#single-line)

## <a name="parts"></a>Parti

`condition` \
Richiesto. Espressione. Deve restituire `True` o `False`oppure a un tipo di dati convertibile in modo implicito in `Boolean`.

Se l'espressione è una variabile [Nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) `Boolean` che restituisce [Nothing](../../../visual-basic/language-reference/nothing.md), la condizione viene considerata come se l'espressione è `False`e i `ElseIf` blocchi vengono valutati se esistono oppure il `Else` blocco è viene eseguito se esistente.

`Then` \
Obbligatorio nella sintassi a riga singola; facoltativo nella sintassi su più righe.

`statements` \
facoltativo. Una o più istruzioni che `If`seguono... che vengono eseguite se `condition` restituisce `True`. `Then`

`elseifcondition` \
Obbligatorio se `ElseIf` è presente. Espressione. Deve restituire `True` o `False`oppure a un tipo di dati convertibile in modo implicito in `Boolean`.

`elseifstatements` \
facoltativo. Una o più istruzioni che `ElseIf`seguono... che vengono eseguite se `elseifcondition` restituisce `True`. `Then`

`elsestatements` \
facoltativo. Una o più istruzioni eseguite se nessuna espressione o `condition` `elseifcondition` precedente restituisce `True`.

`End If` \
Termina la versione multiriga di `If`... `Then`... `Else` blocca.

## <a name="remarks"></a>Note

### <a name="multiline-syntax"></a>Sintassi su più righe

Quando un `If`... `Then`... viene rilevata `condition` l'istruzione, viene testata. `Else` Se `condition` `Then` è `True`, vengono eseguite le istruzioni seguenti. Se `condition` è `False`, ogni`ElseIf` istruzione, se presente, viene valutata in ordine. Quando viene `True` trovato un oggetto `elseifcondition` , vengono eseguite le istruzioni immediatamente `ElseIf` successive all'oggetto associato. Se nessun `elseifcondition` oggetto restituisce `True` ose`Else` non sono presenti istruzioni,verrannoeseguiteleistruzioniseguenti.`ElseIf` Dopo l'esecuzione delle istruzioni che `Then`seguono `ElseIf`, o `Else`, l'esecuzione continua con l'istruzione `End If`seguente.

Le `ElseIf` clausole e `Else` sono entrambe facoltative. È possibile avere `ElseIf` tutte le clausole desiderate `If`in... `Then`... `Else` ma `Else` non `ElseIf` può comparire dopo una clausola. `If`... `Then`... `Else` le istruzioni possono essere nidificate l'una all'altra.

Nella sintassi su più righe, `If` l'istruzione deve essere l'unica istruzione nella prima riga. Le `ElseIf`istruzioni `Else`, e`End If` possono essere precedute solo da un'etichetta di riga. `If`... `Then`... il blocco deve terminare con `End If` un'istruzione. `Else`

> [!TIP]
> L'oggetto [Select... L'istruzione case](../../../visual-basic/language-reference/statements/select-case-statement.md) può essere più utile quando si valuta una singola espressione con diversi valori possibili.

### <a name="single-line-syntax"></a>Sintassi a riga singola

È possibile utilizzare la sintassi a riga singola per una singola condizione con codice da eseguire se è true. Tuttavia, la sintassi a più righe fornisce maggiore struttura e flessibilità ed è più facile da leggere, gestire ed eseguire il debug.

Di seguito viene `Then` esaminata la parola chiave per determinare se un'istruzione è a riga `If`singola. Se viene visualizzato un valore diverso da un `Then` commento dopo sulla stessa riga, l'istruzione viene considerata come un'istruzione a `If` riga singola. Se `Then` è assente, deve essere l'inizio di una riga a più `If`righe... `Then`... `Else`.

Nella sintassi a riga singola è possibile eseguire più istruzioni come risultato di `If`... `Then` decisione. Tutte le istruzioni devono trovarsi sulla stessa riga ed essere separate da due punti.

## <a name="multiline-syntax-example"></a>Esempio di sintassi su più righe

<a name="multi-line"></a>

Nell'esempio seguente viene illustrato l'utilizzo della sintassi multiriga di `If`... `Then`... `Else` istruzione.

[!code-vb[VbVbalrStatements#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#101)]

## <a name="nested-syntax-example"></a>Esempio di sintassi annidata

<a name="nested"></a>

L'esempio seguente contiene un `If`oggetto annidato... `Then`... `Else` istruzioni.

[!code-vb[VbVbalrStatements#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#102)]

## <a name="single-line-syntax-example"></a>Esempio di sintassi a riga singola

<a name="single-line"></a>Nell'esempio seguente viene illustrato l'utilizzo della sintassi a riga singola.

[!code-vb[VbVbalrStatements#103](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#103)]

## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.Interaction.Choose%2A>
- <xref:Microsoft.VisualBasic.Interaction.Switch%2A>
- [Direttive #If...Then...#Else](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [Istruzione Select...Case](../../../visual-basic/language-reference/statements/select-case-statement.md)
- [Strutture di controllo annidate](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [Strutture decisionali](../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [Operatori logici e bit per bit in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
- [Operatore If](../../../visual-basic/language-reference/operators/if-operator.md)
