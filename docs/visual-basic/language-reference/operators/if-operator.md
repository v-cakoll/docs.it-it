---
title: Operatore If (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2c553da5abf5453ba881671806b976125355c1e6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="if-operator-visual-basic"></a>Operatore If (Visual Basic)
Valutazione per restituire in modo condizionale uno dei due valori di corto circuito Usa. Il `If` operatore può essere chiamato con tre argomenti o con due argomenti.  
  
## <a name="syntax"></a>Sintassi  
  
```  
If( [argument1,] argument2, argument3 )  
```  
  
## <a name="if-operator-called-with-three-arguments"></a>Se l'operatore chiamato con tre argomenti  
 Quando `If` viene chiamato con tre argomenti, il primo argomento deve restituire un valore che è possibile eseguire il cast come un `Boolean`. Che `Boolean` valore determina quale dei due argomenti viene valutato e restituito. Nell'elenco seguente viene applicata solo quando il `If` operatore viene chiamato con tre argomenti.  
  
## <a name="parts"></a>Parti  
  
|Termine|Definizione|  
|---|---|  
|`argument1`|Obbligatorio. `Boolean`. Determina quale degli altri argomenti per valutare e restituire.|  
|`argument2`|Obbligatorio. `Object`. Valutata e restituita se `argument1` restituisce `True`.|  
|`argument3`|Obbligatorio. `Object`. Valutata e restituita se `argument1` restituisce `False` o se `argument1` è un [Nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) `Boolean` variabile che restituisce [nulla](../../../visual-basic/language-reference/nothing.md).|  
  
 Un `If` operatore che viene chiamato con tre argomenti funziona come un `IIf` funzione ad eccezione del fatto che usa valutazione di corto circuito. Un `IIf` funzione valuta sempre tutti i tre argomenti, mentre un `If` operatore che ha tre argomenti restituisce solo due di essi. Il primo `If` viene valutato l'argomento e il risultato viene eseguito il cast come un `Boolean` valore `True` o `False`. Se il valore è `True`, `argument2` viene valutato e il relativo valore viene restituito, ma `argument3` non viene valutato. Se il valore della `Boolean` espressione è `False`, `argument3` viene valutato e il relativo valore viene restituito, ma `argument2` non viene valutato. Nell'esempio seguente viene illustrato l'utilizzo di `If` quando vengono utilizzati tre argomenti:  
  
 [!code-vb[VbVbalrOperators#100](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/if-operator_1.vb)]  
  
 Nell'esempio seguente viene illustrato il valore della valutazione di corto circuito. L'esempio mostra due tentativi di dividere una variabile `number` dalla variabile `divisor` eccetto quando `divisor` è zero. In tal caso, deve essere restituito il valore 0, e deve essere eseguito alcun tentativo di eseguire la divisione perché provocherebbe un errore di run-time. Poiché il `If` utilizzo delle espressioni di valutazione di corto circuito, valuta il secondo o il terzo argomento, a seconda del valore del primo argomento. Se il primo argomento è true, è consigliabile valutare il secondo argomento ed eseguire la divisione il divisore è diverso da zero. Se il primo argomento è false, viene valutato solo il terzo argomento e viene restituito 0. Pertanto, quando il divisore è 0, viene eseguito alcun tentativo di eseguire la divisione e non verranno generati errori. Tuttavia, poiché `IIf` non utilizza la valutazione di corto circuito, il secondo argomento viene valutato anche quando il primo argomento è false. Viene generato un errore di divisione per zero in fase di esecuzione.  
  
 [!code-vb[VbVbalrOperators#101](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/if-operator_2.vb)]  
  
## <a name="if-operator-called-with-two-arguments"></a>Se chiamato operatore con due argomenti  
 Il primo argomento `If` può essere omesso. In questo modo l'operatore da chiamare usando solo due argomenti. Nell'elenco seguente viene applicata solo quando il `If` operatore viene chiamato con due argomenti.  
  
## <a name="parts"></a>Parti  
  
|Termine|Definizione|  
|---|---|  
|`argument2`|Obbligatorio. `Object`. Deve essere un riferimento o nullable. Valutata e restituita quando restituisce un valore qualsiasi diverso da `Nothing`.|  
|`argument3`|Obbligatorio. `Object`. Valutata e restituita se `argument2` restituisce `Nothing`.|  
  
 Quando il `Boolean` viene omesso, il primo argomento deve essere un riferimento o nullable. Se il primo argomento restituisce `Nothing`, viene restituito il valore del secondo argomento. In tutti gli altri casi, viene restituito il valore del primo argomento. Nell'esempio seguente viene illustrato il funzionamento di questa valutazione.  
  
 [!code-vb[VbVbalrOperators#102](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/if-operator_3.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:Microsoft.VisualBasic.Interaction.IIf%2A>  
 [Tipi di valori nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)  
 [Nothing](../../../visual-basic/language-reference/nothing.md)
