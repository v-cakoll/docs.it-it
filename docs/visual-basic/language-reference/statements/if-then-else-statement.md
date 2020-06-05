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
ms.openlocfilehash: 0884b71c24742286e695e720add9d00dd4bfe52b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404589"
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

Questo articolo include diversi esempi che illustrano gli usi del `If` ... `Then` ...`Else` istruzione

- [Esempio di sintassi su più righe](#multi-line)
- [Esempio di sintassi annidata](#nested)
- [Esempio di sintassi a riga singola](#single-line)

## <a name="parts"></a>Parti

`condition` \
Obbligatorio. Espressione. Deve restituire `True` o oppure `False` a un tipo di dati convertibile in modo implicito in `Boolean` .

Se l'espressione è una variabile [Nullable](../../programming-guide/language-features/data-types/nullable-value-types.md) `Boolean` che non restituisce [alcun](../nothing.md)valore, la condizione viene considerata come se l'espressione è `False` e i `ElseIf` blocchi vengono valutati se esistono oppure il `Else` blocco viene eseguito se esistente.

`Then` \
Obbligatorio nella sintassi a riga singola; facoltativo nella sintassi su più righe.

`statements` \
Facoltativa. Una o più istruzioni `If` che seguono... `Then` che vengono eseguite se `condition` restituisce `True` .

`elseifcondition` \
Obbligatorio se `ElseIf` è presente. Espressione. Deve restituire `True` o oppure `False` a un tipo di dati convertibile in modo implicito in `Boolean` .

`elseifstatements` \
Facoltativa. Una o più istruzioni `ElseIf` che seguono... `Then` che vengono eseguite se `elseifcondition` restituisce `True` .

`elsestatements` \
Facoltativa. Una o più istruzioni eseguite se nessuna `condition` espressione o precedente `elseifcondition` restituisce `True` .

`End If` \
Termina la versione multiriga di `If` ... `Then` ...`Else` blocco.

## <a name="remarks"></a>Commenti

### <a name="multiline-syntax"></a>Sintassi su più righe

Quando un `If` ... `Then` ...`Else` viene rilevata l'istruzione, `condition` viene testata. Se `condition` è `True` , vengono eseguite le istruzioni seguenti `Then` . Se `condition` è `False` , ogni `ElseIf` istruzione, se presente, viene valutata in ordine. Quando `True` `elseifcondition` viene trovato un oggetto, vengono eseguite le istruzioni immediatamente successive all'oggetto associato `ElseIf` . Se nessun `elseifcondition` `True` oggetto restituisce o se non sono presenti `ElseIf` istruzioni, verranno eseguite le istruzioni seguenti `Else` . Dopo l'esecuzione delle istruzioni che seguono `Then` , `ElseIf` o `Else` , l'esecuzione continua con l'istruzione seguente `End If` .

Le `ElseIf` `Else` clausole e sono entrambe facoltative. È possibile avere tutte le `ElseIf` clausole desiderate in `If` ... `Then` ...`Else` ma non `ElseIf` può comparire dopo una `Else` clausola. `If`...`Then` ...`Else` le istruzioni possono essere nidificate l'una all'altra.

Nella sintassi su più righe, l' `If` istruzione deve essere l'unica istruzione nella prima riga. Le `ElseIf` `Else` istruzioni, e `End If` possono essere precedute solo da un'etichetta di riga. .. `If` . `Then` ...`Else` il blocco deve terminare con un' `End If` istruzione.

> [!TIP]
> L'oggetto [Select... L'istruzione case](select-case-statement.md) può essere più utile quando si valuta una singola espressione con diversi valori possibili.

### <a name="single-line-syntax"></a>Sintassi a riga singola

È possibile utilizzare la sintassi a riga singola per una singola condizione con codice da eseguire se è true. Tuttavia, la sintassi a più righe fornisce maggiore struttura e flessibilità ed è più facile da leggere, gestire ed eseguire il debug.

`Then`Di seguito viene esaminata la parola chiave per determinare se un'istruzione è a riga singola `If` . Se viene visualizzato un valore diverso da un commento dopo `Then` sulla stessa riga, l'istruzione viene considerata come un'istruzione a riga singola `If` . Se `Then` è assente, deve essere l'inizio di una riga a più righe `If` ... `Then` ...`Else`.

Nella sintassi a riga singola è possibile eseguire più istruzioni come risultato di una `If` decisione... `Then` . Tutte le istruzioni devono trovarsi sulla stessa riga ed essere separate da due punti.

## <a name="multiline-syntax-example"></a>Esempio di sintassi su più righe

<a name="multi-line"></a>

Nell'esempio seguente viene illustrato l'utilizzo della sintassi multiriga di `If` ... `Then` ...`Else` istruzione.

[!code-vb[VbVbalrStatements#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#101)]

## <a name="nested-syntax-example"></a>Esempio di sintassi annidata

<a name="nested"></a>

L'esempio seguente contiene un oggetto annidato `If` ... `Then` ...`Else` istruzioni.

[!code-vb[VbVbalrStatements#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#102)]

## <a name="single-line-syntax-example"></a>Esempio di sintassi a riga singola

<a name="single-line"></a>Nell'esempio seguente viene illustrato l'utilizzo della sintassi a riga singola.

[!code-vb[VbVbalrStatements#103](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#103)]

## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.Interaction.Choose%2A>
- <xref:Microsoft.VisualBasic.Interaction.Switch%2A>
- [#If... Direttive then... #Else](../directives/if-then-else-directives.md)
- [Istruzione Select...Case](select-case-statement.md)
- [Strutture di controllo annidate](../../programming-guide/language-features/control-flow/nested-control-structures.md)
- [Strutture decisionali](../../programming-guide/language-features/control-flow/decision-structures.md)
- [Operatori logici e bit per bit in Visual Basic](../../programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
- [Operatore If](../operators/if-operator.md)
