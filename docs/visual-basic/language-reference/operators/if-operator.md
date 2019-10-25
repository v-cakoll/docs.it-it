---
title: Operatore If (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.IfOperator
- IfOperator
helpviewer_keywords:
- ternary operators [Visual Basic]
- conditional execution
- If expressions [Visual Basic]
- conditional operator [Visual Basic]
- If Operator [Visual Basic]
ms.assetid: dd56c9df-7cd4-442c-9ba6-20c70ee44c8f
ms.openlocfilehash: 483b58dd9c79c716fdc3d272cf699e33dec9c671
ms.sourcegitcommit: 9bd1c09128e012b6e34bdcbdf3576379f58f3137
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/23/2019
ms.locfileid: "72799007"
---
# <a name="if-operator-visual-basic"></a>Operatore If (Visual Basic)

Usa la valutazione del cortocircuito per restituire in modo condizionale uno dei due valori. L'operatore `If` può essere chiamato con tre argomenti o con due argomenti.

## <a name="syntax"></a>Sintassi

```vb
If( [argument1,] argument2, argument3 )
```

## <a name="if-operator-called-with-three-arguments"></a>Operatore If chiamato con tre argomenti

Quando `If` viene chiamato con tre argomenti, il primo argomento deve restituire un valore di cui è possibile eseguire il cast come `Boolean`. Che `Boolean` valore determinerà quale degli altri due argomenti viene valutato e restituito. L'elenco seguente si applica solo quando l'operatore `If` viene chiamato utilizzando tre argomenti.

### <a name="parts"></a>Parti

|Termine|Definizione|
|---|---|
|`argument1`|Obbligatorio. `Boolean` Determina quale degli altri argomenti valutare e restituire.|
|`argument2`|Obbligatorio. `Object` Valutato e restituito se `argument1` restituisce `True`.|
|`argument3`|Obbligatorio. `Object` Valutato e restituito se `argument1` restituisce `False` o se `argument1` è una variabile`Boolean` [Nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) che [non restituisce alcun](../../../visual-basic/language-reference/nothing.md)valore.|

Un operatore `If` chiamato con tre argomenti funziona come una funzione `IIf` ad eccezione del fatto che usa la valutazione a corto circuito. Una funzione `IIf` valuta sempre tutti e tre gli argomenti, mentre un operatore `If` con tre argomenti ne valuta solo due. Il primo argomento `If` viene valutato e viene eseguito il cast del risultato come valore `Boolean`, `True` o `False`. Se il valore è `True`, `argument2` viene valutato e viene restituito il relativo valore, ma `argument3` non viene valutato. Se il valore dell'espressione `Boolean` è `False`, `argument3` viene valutato e viene restituito il relativo valore, ma `argument2` non viene valutato. Negli esempi seguenti viene illustrato l'utilizzo di `If` quando vengono utilizzati tre argomenti:

[!code-vb[VbVbalrOperators#100](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class4.vb#100)]

Nell'esempio seguente viene illustrato il valore della valutazione del cortocircuito. Nell'esempio vengono illustrati due tentativi di dividere la variabile `number` in base alla variabile `divisor` tranne quando `divisor` è zero. In tal caso, deve essere restituito 0 e non è necessario effettuare alcuna operazione per eseguire la divisione perché si verificherà un errore in fase di esecuzione. Poiché l'espressione `If` usa la valutazione di corto circuito, viene valutato il secondo o il terzo argomento, a seconda del valore del primo argomento. Se il primo argomento è true, il divisore è diverso da zero ed è sicuro valutare il secondo argomento ed eseguire la divisione. Se il primo argomento è false, viene valutato solo il terzo argomento e viene restituito 0. Pertanto, quando il divisore è 0, non viene effettuato alcun tentativo di eseguire la divisione e non vengono restituiti errori. Tuttavia, poiché `IIf` non utilizza la valutazione del cortocircuito, il secondo argomento viene valutato anche quando il primo argomento è false. Causando un errore di divisione per zero della fase di esecuzione.

[!code-vb[VbVbalrOperators#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class4.vb#101)]

## <a name="if-operator-called-with-two-arguments"></a>Operatore If chiamato con due argomenti

Il primo argomento per `If` può essere omesso. In questo modo è possibile chiamare l'operatore utilizzando solo due argomenti. L'elenco seguente si applica solo quando l'operatore `If` viene chiamato con due argomenti.

### <a name="parts"></a>Parti

|Termine|Definizione|
|---|---|
|`argument2`|Obbligatorio. `Object` Deve essere un riferimento o un tipo Nullable. Valutato e restituito quando restituisce un valore diverso da `Nothing`.|
|`argument3`|Obbligatorio. `Object` Valutato e restituito se `argument2` restituisce `Nothing`.|

Quando l'argomento `Boolean` viene omesso, il primo argomento deve essere un riferimento o un tipo Nullable. Se il primo argomento restituisce `Nothing`, viene restituito il valore del secondo argomento. In tutti gli altri casi, viene restituito il valore del primo argomento. Nell'esempio seguente viene illustrato il funzionamento della valutazione:

[!code-vb[VbVbalrOperators#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class4.vb#102)]

## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.Interaction.IIf%2A>
- [Tipi di valori nullable](../../programming-guide/language-features/data-types/nullable-value-types.md)
- [Nothing](../nothing.md)
