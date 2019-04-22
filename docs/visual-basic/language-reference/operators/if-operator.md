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
ms.openlocfilehash: 9ab01755d75c91ce87acf83e7f406b26c466aef6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58834634"
---
# <a name="if-operator-visual-basic"></a>Operatore If (Visual Basic)
Utilizzi di corto circuito di valutazione per restituire in modo condizionale uno dei due valori. Il `If` operatore può essere chiamato con tre argomenti o con due argomenti.  
  
## <a name="syntax"></a>Sintassi  
  
```  
If( [argument1,] argument2, argument3 )  
```  
  
## <a name="if-operator-called-with-three-arguments"></a>Se viene chiamato operatore con tre argomenti  
 Quando `If` viene chiamato con tre argomenti, il primo argomento deve restituire un valore che è possibile eseguire il cast come un `Boolean`. Che `Boolean` valore determina quale dei due argomenti viene valutata e restituita. Nell'elenco seguente si applica solo quando il `If` operatore viene chiamato con tre argomenti.  
  
## <a name="parts"></a>Parti  
  
|Termine|Definizione|  
|---|---|  
|`argument1`|Obbligatorio. `Boolean`. Determina gli altri argomenti per valutare e restituire.|  
|`argument2`|Obbligatorio. `Object`. Valutata e restituita se `argument1` restituisca `True`.|  
|`argument3`|Obbligatorio. `Object`. Valutata e restituita se `argument1` restituisca `False` o se `argument1` è un [Nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) `Boolean` variabile che restituisca [Nothing](../../../visual-basic/language-reference/nothing.md).|  
  
 Un' `If` operatore che viene chiamato con tre argomenti funziona come un `IIf` funzioni ad eccezione del fatto che usi valutazione di corto circuito. Un' `IIf` funzione valuta sempre tutti e tre argomenti, mentre un `If` operatore con tre argomenti viene valutata solo due di essi. Il primo `If` viene valutato l'argomento e il risultato viene eseguito il cast come un `Boolean` , valore `True` o `False`. Se il valore è `True`, `argument2` viene valutata e il relativo valore viene restituito, ma `argument3` non viene valutato. Se il valore della `Boolean` espressione è `False`, `argument3` viene valutata e il relativo valore viene restituito, ma `argument2` non viene valutato. Gli esempi seguenti illustrano l'uso di `If` quando vengono usati tre argomenti:  
  
 [!code-vb[VbVbalrOperators#100](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class4.vb#100)]  
  
 L'esempio seguente illustra il valore di valutazione di corto circuito. L'esempio mostra due tentativi di dividere una variabile `number` dalla variabile `divisor` eccetto quando `divisor` è uguale a zero. In tal caso, deve essere restituito un valore 0 e debba eseguito alcun tentativo di eseguire la divisione perché provocherebbe un errore di run-time. Poiché il `If` utilizzo delle espressioni di valutazione di corto circuito, valuta il secondo o il terzo argomento, a seconda del valore del primo argomento. Se il primo argomento è true, il divisore è diverso da zero ed è opportuno valutare il secondo argomento ed eseguire la divisione. Se il primo argomento è false, solo il terzo argomento viene valutato e viene restituito 0. Pertanto, quando il divisore è 0, viene eseguito alcun tentativo di eseguire la divisione e non verranno generati errori. Tuttavia, poiché `IIf` non usa la valutazione di corto circuito, il secondo argomento è valutato anche quando il primo argomento è false. Ciò causa un errore di divisione per zero in fase di esecuzione.  
  
 [!code-vb[VbVbalrOperators#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class4.vb#101)]  
  
## <a name="if-operator-called-with-two-arguments"></a>Se viene chiamato operatore con due argomenti  
 Il primo argomento `If` può essere omesso. In questo modo l'operatore di chiamata usando solo due argomenti. Nell'elenco seguente si applica solo quando il `If` operatore viene chiamato con due argomenti.  
  
## <a name="parts"></a>Parti  
  
|Termine|Definizione|  
|---|---|  
|`argument2`|Obbligatorio. `Object`. Deve essere un riferimento o nullable. Valutata e restituita quando restituisce un valore qualsiasi diverso da `Nothing`.|  
|`argument3`|Obbligatorio. `Object`. Valutata e restituita se `argument2` restituisca `Nothing`.|  
  
 Quando il `Boolean` viene omesso, il primo argomento deve essere un riferimento o nullable. Se il primo argomento restituisce `Nothing`, viene restituito il valore del secondo argomento. In tutti gli altri casi, viene restituito il valore del primo argomento. L'esempio seguente illustra il funzionamento di questa versione di valutazione.  
  
 [!code-vb[VbVbalrOperators#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class4.vb#102)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.Interaction.IIf%2A>
- [Tipi di valori nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [Nothing](../../../visual-basic/language-reference/nothing.md)
