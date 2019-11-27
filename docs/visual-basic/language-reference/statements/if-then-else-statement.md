---
title: Istruzione If...Then...Else
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
ms.openlocfilehash: f505755caeb9cc3cfeeb1ba83b6de15f48314103
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351168"
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

Questo articolo include diversi esempi che illustrano gli usi dell'istruzione `If`...`Then`...`Else`:

- [Esempio di sintassi su più righe](#multi-line)
- [Esempio di sintassi annidata](#nested)
- [Esempio di sintassi a riga singola](#single-line)

## <a name="parts"></a>Parti

`condition` \
Obbligatoria. Espressione. Deve restituire `True` o `False`o a un tipo di dati convertibile in modo implicito in `Boolean`.

Se l'espressione è una variabile di `Boolean` [Nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) che non restituisce [alcun](../../../visual-basic/language-reference/nothing.md)valore, la condizione viene considerata come se l'espressione venisse `False`e i blocchi di `ElseIf` vengono valutati se esistono o se il `Else` blocco viene eseguito se esiste.

`Then` \
Obbligatorio nella sintassi a riga singola; facoltativo nella sintassi su più righe.

`statements` \
Facoltativa. Una o più istruzioni che seguono `If`...`Then` che vengono eseguite se `condition` restituisce `True`.

`elseifcondition` \
Obbligatorio se è presente `ElseIf`. Espressione. Deve restituire `True` o `False`o a un tipo di dati convertibile in modo implicito in `Boolean`.

`elseifstatements` \
Facoltativa. Una o più istruzioni che seguono `ElseIf`...`Then` che vengono eseguite se `elseifcondition` restituisce `True`.

`elsestatements` \
Facoltativa. Una o più istruzioni eseguite se nessuna `condition` o espressione `elseifcondition` precedente restituisce `True`.

`End If` \
Termina la versione multiriga del blocco `If`...`Then`...`Else`.

## <a name="remarks"></a>Note

### <a name="multiline-syntax"></a>Sintassi su più righe

Quando viene rilevata un'istruzione `If`...`Then`...`Else`, `condition` viene testato. Se `condition` è `True`, vengono eseguite le istruzioni che seguono `Then`. Se `condition` è `False`, ogni istruzione `ElseIf`, se presente, viene valutata in ordine. Quando viene individuato un `True` `elseifcondition`, vengono eseguite le istruzioni immediatamente successive al `ElseIf` associato. Se nessuna `elseifcondition` restituisce `True`o se non sono presenti istruzioni `ElseIf`, vengono eseguite le istruzioni che seguono `Else`. Dopo aver eseguito le istruzioni che seguono `Then`, `ElseIf`o `Else`, l'esecuzione continua con l'istruzione che segue `End If`.

Le clausole `ElseIf` e `Else` sono entrambe facoltative. In un'istruzione `If`...`Then`...`Else` è possibile avere un numero di clausole di `ElseIf`, ma non è possibile visualizzare una clausola `ElseIf` dopo una clausola `Else`. le istruzioni `If`...`Then`...`Else` possono essere annidate l'una all'altra.

Nella sintassi su più righe, l'istruzione `If` deve essere l'unica istruzione nella prima riga. Le istruzioni `ElseIf`, `Else`e `End If` possono essere precedute solo da un'etichetta di riga. Il blocco `If`...`Then`...`Else` deve terminare con un'istruzione `End If`.

> [!TIP]
> L'oggetto [Select... L'istruzione case](../../../visual-basic/language-reference/statements/select-case-statement.md) può essere più utile quando si valuta una singola espressione con diversi valori possibili.

### <a name="single-line-syntax"></a>Sintassi a riga singola

È possibile utilizzare la sintassi a riga singola per una singola condizione con codice da eseguire se è true. Tuttavia, la sintassi a più righe fornisce maggiore struttura e flessibilità ed è più facile da leggere, gestire ed eseguire il debug.

Di seguito viene esaminata la parola chiave `Then` per determinare se un'istruzione è una `If`a riga singola. Se non viene visualizzato alcun commento dopo `Then` sulla stessa riga, l'istruzione viene considerata come un'istruzione `If` a riga singola. Se `Then` è assente, deve essere l'inizio di un `If`a più righe...`Then`...`Else`.

Nella sintassi a riga singola è possibile avere più istruzioni eseguite come risultato di una decisione `If`...`Then`. Tutte le istruzioni devono trovarsi sulla stessa riga ed essere separate da due punti.

## <a name="multiline-syntax-example"></a>Esempio di sintassi su più righe

<a name="multi-line"></a>

Nell'esempio seguente viene illustrato l'utilizzo della sintassi su più righe dell'istruzione `If`...`Then`...`Else`.

[!code-vb[VbVbalrStatements#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#101)]

## <a name="nested-syntax-example"></a>Esempio di sintassi annidata

<a name="nested"></a>

Nell'esempio seguente sono contenute le istruzioni annidate `If`...`Then`...`Else`.

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
