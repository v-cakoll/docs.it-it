---
title: Operatore If
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
ms.openlocfilehash: 3b45a5afe331bd00c2b92f8c305351b77bc319cf
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249487"
---
# <a name="if-operator-visual-basic"></a>Operatore If (Visual Basic)

Utilizza la valutazione del corto circuito per restituire in modo condizionale uno dei due valori. L'operatore `If` può essere chiamato con tre argomenti o con due argomenti.

## <a name="syntax"></a>Sintassi

```vb
If( [argument1,] argument2, argument3 )
```

## <a name="if-operator-called-with-three-arguments"></a>Operatore If chiamato con tre argomenti

Quando `If` viene chiamato utilizzando tre argomenti, il primo argomento deve restituire `Boolean`un valore di cui è possibile eseguire il cast come oggetto . Tale `Boolean` valore determinerà quale degli altri due argomenti viene valutato e restituito. L'elenco seguente si `If` applica solo quando l'operatore viene chiamato utilizzando tre argomenti.

### <a name="parts"></a>Parti

|Termine|Definizione|
|---|---|
|`argument1`|Obbligatorio. `Boolean`. Determina quale degli altri argomenti valutare e restituire.|
|`argument2`|Obbligatorio. `Object`. Valutato e restituito `argument1` se `True`restituisce .|
|`argument3`|Obbligatorio. `Object`. Valutato e restituito `argument1` se `False` restituisce `argument1` o se è una variabile [Nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) `Boolean` che restituisce [Nothing](../../../visual-basic/language-reference/nothing.md).|

Un `If` operatore chiamato con tre `IIf` argomenti funziona come una funzione, ad eccezione del fatto che utilizza la valutazione a corto circuito. Una `IIf` funzione valuta sempre tutti e tre `If` i relativi argomenti, mentre un operatore con tre argomenti ne valuta solo due. Il `If` primo argomento viene valutato e `Boolean` viene `True` eseguito il cast del risultato come valore, o `False`. Se il `True`valore `argument2` è , viene valutato e `argument3` ne viene restituito il valore, ma non viene valutato. Se il valore `Boolean` dell'espressione è `False`, `argument3` viene valutato `argument2` e ne viene restituito il valore, ma non viene valutato. Negli esempi seguenti viene `If` illustrato l'utilizzo di quando vengono utilizzati tre argomenti:

[!code-vb[VbVbalrOperators#100](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class4.vb#100)]

Nell'esempio seguente viene illustrato il valore della valutazione dei corto circuito. L'esempio mostra due `number` tentativi `divisor` di `divisor` dividere la variabile per variabile tranne quando è zero. In tal caso, deve essere restituito uno 0 e non deve essere effettuato alcun tentativo di eseguire la divisione perché si potrebbe verificare un errore di run-time. Poiché `If` l'espressione utilizza la valutazione a corto circuito, valuta il secondo o il terzo argomento, a seconda del valore del primo argomento. Se il primo argomento è true, il divisore è diverso da zero ed è sicuro valutare il secondo argomento ed eseguire la divisione. Se il primo argomento è false, viene valutato solo il terzo argomento e viene restituito uno 0. Pertanto, quando il divisore è 0, non viene effettuato alcun tentativo di eseguire la divisione e non viene visualizzato alcun risultato di errore. Tuttavia, `IIf` poiché non utilizza la valutazione del corto circuito, il secondo argomento viene valutato anche quando il primo argomento è false. In questo modo un errore di divisione in fase di esecuzione per zero.

[!code-vb[VbVbalrOperators#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class4.vb#101)]

## <a name="if-operator-called-with-two-arguments"></a>Operatore If chiamato con due argomenti

Il primo `If` argomento da può essere omesso. In questo modo l'operatore può essere chiamato utilizzando solo due argomenti. L'elenco seguente si `If` applica solo quando l'operatore viene chiamato con due argomenti.

### <a name="parts"></a>Parti

|Termine|Definizione|
|---|---|
|`argument2`|Obbligatorio. `Object`. Deve essere un tipo di valore a cui è possibile essere un riferimento o un tipo di valore nullable. Valutato e restituito quando restituisce un `Nothing`valore diverso da .|
|`argument3`|Obbligatorio. `Object`. Valutato e restituito `argument2` se `Nothing`restituisce .|

Quando `Boolean` l'argomento viene omesso, il primo argomento deve essere un tipo di valore a cui si fa riferimento o nullable. Se il primo argomento `Nothing`restituisce , viene restituito il valore del secondo argomento. In tutti gli altri casi, viene restituito il valore del primo argomento. L'esempio seguente illustra il funzionamento di questa valutazione:The following example illustrates how this evaluation works:

[!code-vb[VbVbalrOperators#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class4.vb#102)]

## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.Interaction.IIf%2A>
- [Tipi di valore nullableNullable Value Types](../../programming-guide/language-features/data-types/nullable-value-types.md)
- [Niente](../nothing.md)
