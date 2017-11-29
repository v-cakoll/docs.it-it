---
title: Operatore OrElse (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- OrElse
- vb.OrElse
helpviewer_keywords:
- short-circuiting
- operators [Visual Basic], short-circuiting
- operators [Visual Basic], disjunction
- short-circuit evaluation
- OrElse operator [Visual Basic]
ms.assetid: 253803d8-05b0-47d7-b213-abd222847779
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 47239a1d2b5b20f2b8cacc9b9185a0f95f63dc84
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="orelse-operator-visual-basic"></a>Operatore OrElse (Visual Basic)
Esegue la disgiunzione logica inclusiva su due espressioni di corto circuito.  
  
## <a name="syntax"></a>Sintassi  
  
```  
result = expression1 OrElse expression2  
```  
  
## <a name="parts"></a>Parti  
 `result`  
 Obbligatorio. Qualsiasi espressione `Boolean`.  
  
 `expression1`  
 Obbligatorio. Qualsiasi espressione `Boolean`.  
  
 `expression2`  
 Obbligatorio. Qualsiasi espressione `Boolean`.  
  
## <a name="remarks"></a>Note  
 Viene definita un'operazione logica *corto circuito* se il codice compilato può ignorare la valutazione di un'espressione in base al risultato di un'altra espressione. Se il risultato della prima espressione valutata determina il risultato finale dell'operazione, è necessario valutare l'espressione della seconda, perché non è possibile modificare il risultato finale. Corto circuito può migliorare le prestazioni se l'espressione ignorata è complessa o se include le chiamate di procedura.  
  
 Se una o entrambe le espressioni restituiscono `True`, `result` è `True`. Nella tabella seguente viene illustrato come `result` è determinata.  
  
|Se `expression1` è|E `expression2` è|Il valore di `result` è|  
|-------------------------|--------------------------|------------------------------|  
|`True`|(non valutato)|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
## <a name="data-types"></a>Tipi di dati  
 Il `OrElse` è definito solo per il [tipo di dati Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md). Visual Basic converte ogni operando in base alle esigenze per `Boolean` e l'operazione viene eseguita interamente in `Boolean`. Se si assegna il risultato a un tipo numerico, Visual Basic viene convertito da `Boolean` a tale tipo. Questa operazione può generare un comportamento imprevisto. Ad esempio, `5 OrElse 12` comporta `–1` quando convertito in `Integer`.  
  
## <a name="overloading"></a>Overload  
 Il [operatore o](../../../visual-basic/language-reference/operators/or-operator.md) e [Operatore IsTrue](../../../visual-basic/language-reference/operators/istrue-operator.md) può essere *overload*, il che significa che una classe o struttura possibile ridefinirne il comportamento quando il tipo di tale classe dispone di un operando o struttura. L'overload di `Or` e `IsTrue` operatori influisce sul comportamento del `OrElse` operatore. Se il codice utilizza `OrElse` in una classe o struttura che esegue l'overload `Or` e `IsTrue`, assicurarsi di comprendere il comportamento ridefinito. Per ulteriori informazioni, vedere [routine di operatore](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il `OrElse` operatore per eseguire la disgiunzione logica tra due espressioni. Il risultato è un `Boolean` valore che rappresenta se viene soddisfatta una delle due espressioni. Se la prima espressione è `True`, la seconda non viene valutata.  
  
 [!code-vb[VbVbalrOperators#37](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/orelse-operator_1.vb)]  
  
 Nell'esempio precedente produce i risultati di `True`, `True`, e `False` rispettivamente. Nel calcolo della `firstCheck`, la seconda espressione non viene valutata in quanto il primo è già `True`. Tuttavia, la seconda espressione viene valutata nel calcolo della `secondCheck`.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente un `If`... `Then` istruzione contenente due chiamate di routine. Se la prima chiamata restituisce `True`, la seconda procedura non viene chiamata. Questo può produrre risultati imprevisti se la seconda procedura esegue attività importanti che devono sempre essere eseguite durante l'esecuzione di questa sezione del codice.  
  
 [!code-vb[VbVbalrOperators#38](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/orelse-operator_2.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Operatori logici e bit per bit (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)  
 [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Operatore Or](../../../visual-basic/language-reference/operators/or-operator.md)  
 [Operatore IsTrue](../../../visual-basic/language-reference/operators/istrue-operator.md)  
 [Operatori logici e bit per bit in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
