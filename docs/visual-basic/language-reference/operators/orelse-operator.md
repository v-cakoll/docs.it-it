---
title: Operatore OrElse (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: 28d1481b71979936bb16a2ecfb1140d85a674ef7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58816395"
---
# <a name="orelse-operator-visual-basic"></a>Operatore OrElse (Visual Basic)
Esegue una disgiunzione logica inclusiva su due espressioni di corto circuito.  
  
## <a name="syntax"></a>Sintassi  
  
```  
result = expression1 OrElse expression2  
```  
  
## <a name="parts"></a>Parti  
 `result`  
 Obbligatorio. Qualsiasi espressione `Boolean` .  
  
 `expression1`  
 Obbligatorio. Qualsiasi espressione `Boolean` .  
  
 `expression2`  
 Obbligatorio. Qualsiasi espressione `Boolean` .  
  
## <a name="remarks"></a>Note  
 Un'operazione logica viene detto *corto circuito* se il codice compilato può ignorare la valutazione di un'espressione in base al risultato di un'altra espressione. Se il risultato della prima espressione valutata determina il risultato finale dell'operazione, non è necessario per valutare la seconda espressione, in quanto non può modificare il risultato finale. Corto circuito può migliorare le prestazioni se l'espressione ignorato è complesso, o se prevede le chiamate di procedura.  
  
 Se una o entrambe le espressioni restituiscono `True`, `result` è `True`. La tabella seguente illustra come `result` è determinata.  
  
|Se `expression1` è|E `expression2` è|Il valore di `result` è|  
|-------------------------|--------------------------|------------------------------|  
|`True`|(non valutati)|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
## <a name="data-types"></a>Tipi di dati  
 Il `OrElse` operatore è definito solo per il [tipo di dati Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md). Visual Basic consente di convertire ogni operando in base alle esigenze per `Boolean` ed esegue l'operazione interamente in `Boolean`. Se si assegna il risultato a un tipo numerico, Visual Basic viene convertito da `Boolean` per quel tipo. Questa operazione può generare un comportamento imprevisto. Ad esempio, `5 OrElse 12` comporterà `–1` quando convertito in `Integer`.  
  
## <a name="overloading"></a>Overload  
 Il [operatore Or](../../../visual-basic/language-reference/operators/or-operator.md) e il [Operatore IsTrue](../../../visual-basic/language-reference/operators/istrue-operator.md) può essere *sottoposti a overload*, il che significa che una classe o struttura può ridefinire il comportamento quando un operando ha il tipo di tale classe o una struttura. L'overload di `Or` e `IsTrue` operatori influisce sul comportamento del `OrElse` operatore. Se il codice usi `OrElse` in una classe o struttura che esegue l'overload `Or` e `IsTrue`, assicurarsi di comprendere il comportamento ridefinito. Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il `OrElse` operatore per eseguire la disgiunzione logica tra due espressioni. Il risultato è un `Boolean` valore che rappresenta se viene soddisfatta una delle due espressioni. Se la prima espressione è `True`, la seconda non viene valutata.  
  
 [!code-vb[VbVbalrOperators#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#37)]  
  
 Nell'esempio precedente produce i risultati dei `True`, `True`, e `False` rispettivamente. Nel calcolo della `firstCheck`, la seconda espressione non viene valutata il primo è già `True`. Tuttavia, la seconda espressione viene valutata nel calcolo della `secondCheck`.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente mostra un `If`... `Then` istruzione che contiene due chiamate di procedura. Se la prima chiamata restituisce `True`, la seconda procedura non viene chiamata. Ciò potrebbe produrre risultati imprevisti se la seconda procedura esegue le attività importanti che devono essere sempre eseguite quando viene eseguito in questa sezione del codice.  
  
 [!code-vb[VbVbalrOperators#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#38)]  
  
## <a name="see-also"></a>Vedere anche

- [Operatori logici e bit per bit (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Operatore Or](../../../visual-basic/language-reference/operators/or-operator.md)
- [Operatore IsTrue](../../../visual-basic/language-reference/operators/istrue-operator.md)
- [Operatori logici e bit per bit in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
