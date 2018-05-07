---
title: Operatore AndAlso (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.AndAlso
- AndAlso
helpviewer_keywords:
- short-circuiting
- AndAlso operator [Visual Basic]
- operators [Visual Basic], short-circuiting
- operators [Visual Basic], conjunction
- short-circuit evaluation
ms.assetid: bbc15191-b374-495b-9b8f-7b8c2f4388eb
ms.openlocfilehash: 549d14cc35d285ac2e4a02a37dd201cc669c5627
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="andalso-operator-visual-basic"></a>Operatore AndAlso (Visual Basic)
Esegue una congiunzione logica su due espressioni.  
  
## <a name="syntax"></a>Sintassi  
  
```  
result = expression1 AndAlso expression2  
```  
  
## <a name="parts"></a>Parti  
  
|Termine|Definizione|  
|---|---|  
|`result`|Obbligatorio. Qualsiasi espressione `Boolean`. Il risultato è il `Boolean` risultato del confronto di due espressioni.|  
|`expression1`|Obbligatorio. Qualsiasi espressione `Boolean`.|  
|`expression2`|Obbligatorio. Qualsiasi espressione `Boolean`.|  
  
## <a name="remarks"></a>Note  
 Viene definita un'operazione logica *corto circuito* se il codice compilato può ignorare la valutazione di un'espressione in base al risultato di un'altra espressione. Se il risultato della prima espressione valutata determina il risultato finale dell'operazione, è necessario valutare l'espressione della seconda, perché non è possibile modificare il risultato finale. Corto circuito può migliorare le prestazioni se l'espressione ignorata è complessa o se include le chiamate di procedura.  
  
 Se entrambe le espressioni restituiscono `True`, `result` è `True`. Nella tabella seguente viene illustrato come `result` è determinata.  
  
|Se `expression1` è|E `expression2` è|Il valore di `result` è|  
|---|---|---|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|(non valutato)|`False`|  
  
## <a name="data-types"></a>Tipi di dati  
 Il `AndAlso` è definito solo per il [tipo di dati Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md). Visual Basic converte ogni operando in base alle esigenze per `Boolean` e l'operazione viene eseguita interamente in `Boolean`. Se si assegna il risultato a un tipo numerico, Visual Basic viene convertito da `Boolean` a tale tipo. Questa operazione può generare un comportamento imprevisto. Ad esempio, `5 AndAlso 12` comporta `–1` quando convertito in `Integer`.  
  
## <a name="overloading"></a>Overload  
 Il [operatore e](../../../visual-basic/language-reference/operators/and-operator.md) e [Operatore IsFalse](../../../visual-basic/language-reference/operators/isfalse-operator.md) può essere *overload*, il che significa che una classe o struttura possibile ridefinirne il comportamento quando il tipo di oggetto che dispone di un operando classe o struttura. L'overload di `And` e `IsFalse` operatori influisce sul comportamento del `AndAlso` operatore. Se il codice utilizza `AndAlso` in una classe o struttura che esegue l'overload `And` e `IsFalse`, assicurarsi di comprendere il comportamento ridefinito. Per ulteriori informazioni, vedere [routine di operatore](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il `AndAlso` operatore per eseguire una congiunzione logica tra due espressioni. Il risultato è un `Boolean` valore che indica se l'intera espressione di congiunzione è true. Se la prima espressione è `False`, la seconda non viene valutata.  
  
 [!code-vb[VbVbalrOperators#24](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/andalso-operator_1.vb)]  
  
 Nell'esempio precedente produce i risultati di `True`, `False`, e `False`, rispettivamente. Nel calcolo della `secondCheck`, la seconda espressione non viene valutata in quanto il primo è già `False`. Tuttavia, la seconda espressione viene valutata nel calcolo della `thirdCheck`.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente un `Function` routine che esegue la ricerca di un determinato valore tra gli elementi della matrice. Se la matrice è vuota o se viene superata la lunghezza della matrice, il `While` istruzione non testa l'elemento della matrice rispetto al valore di ricerca.  
  
 [!code-vb[VbVbalrOperators#25](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/andalso-operator_2.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Operatori logici e bit per bit (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)  
 [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Operatore And](../../../visual-basic/language-reference/operators/and-operator.md)  
 [Operatore IsFalse](../../../visual-basic/language-reference/operators/isfalse-operator.md)  
 [Operatori logici e bit per bit in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
