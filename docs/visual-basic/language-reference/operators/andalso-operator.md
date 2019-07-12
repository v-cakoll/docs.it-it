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
ms.openlocfilehash: 1cb4d372d3ac228f29c6fa45f124796e5dfb6709
ms.sourcegitcommit: 83ecdf731dc1920bca31f017b1556c917aafd7a0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2019
ms.locfileid: "67859890"
---
# <a name="andalso-operator-visual-basic"></a>Operatore AndAlso (Visual Basic)
Esegue la congiunzione logica su due espressioni.  
  
## <a name="syntax"></a>Sintassi  
  
```vb
result = expression1 AndAlso expression2  
```  
  
## <a name="parts"></a>Parti  
  
|Termine|Definizione|  
|---|---|  
|`result`|Richiesto. Qualsiasi espressione `Boolean` . Il risultato è il `Boolean` risultato del confronto delle due espressioni.|  
|`expression1`|Richiesto. Qualsiasi espressione `Boolean` .|  
|`expression2`|Richiesto. Qualsiasi espressione `Boolean` .|  
  
## <a name="remarks"></a>Note  
 Un'operazione logica viene detto *corto circuito* se il codice compilato può ignorare la valutazione di un'espressione in base al risultato di un'altra espressione. Se il risultato della prima espressione valutata determina il risultato finale dell'operazione, non è necessario per valutare la seconda espressione, in quanto non può modificare il risultato finale. Corto circuito può migliorare le prestazioni se l'espressione ignorato è complesso, o se prevede le chiamate di procedura.  
  
 Se entrambe le espressioni restituiscono `True`, `result` è `True`. La tabella seguente illustra come `result` è determinata.  
  
|Se `expression1` è|E `expression2` è|Il valore di `result` è|  
|---|---|---|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|(non valutati)|`False`|  
  
## <a name="data-types"></a>Tipi di dati  
 Il `AndAlso` operatore è definito solo per il [tipo di dati Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md). Visual Basic consente di convertire ogni operando in base alle esigenze per `Boolean` prima della valutazione dell'espressione. Se si assegna il risultato a un tipo numerico, Visual Basic viene convertito da `Boolean` per quel tipo in modo che `False` diventa `0` e `True` diventa `-1`.
Per altre informazioni, vedere [conversioni dei tipi booleani](../data-types/boolean-data-type.md#type-conversions)
  
## <a name="overloading"></a>Overload  
 Il [operatore And](../../../visual-basic/language-reference/operators/and-operator.md) e il [Operatore IsFalse](../../../visual-basic/language-reference/operators/isfalse-operator.md) può essere *sottoposti a overload*, il che significa che una classe o struttura può ridefinire il comportamento quando un operando ha il tipo di oggetto che classe o struttura. L'overload di `And` e `IsFalse` operatori influisce sul comportamento del `AndAlso` operatore. Se il codice usi `AndAlso` in una classe o struttura che esegue l'overload `And` e `IsFalse`, assicurarsi di comprendere il comportamento ridefinito. Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il `AndAlso` operatore per eseguire una congiunzione logica su due espressioni. Il risultato è un `Boolean` valore che indica se l'intera espressione di congiunzione è true. Se la prima espressione è `False`, la seconda non viene valutata.  
  
 [!code-vb[VbVbalrOperators#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#24)]  
  
 Nell'esempio precedente produce i risultati dei `True`, `False`, e `False`, rispettivamente. Nel calcolo della `secondCheck`, la seconda espressione non viene valutata il primo è già `False`. Tuttavia, la seconda espressione viene valutata nel calcolo della `thirdCheck`.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente mostra un `Function` procedure che esegue la ricerca per un determinato valore tra gli elementi della matrice. Se la matrice è vuota o se viene superata la lunghezza della matrice, il `While` istruzione non testa l'elemento della matrice rispetto al valore di ricerca.  
  
 [!code-vb[VbVbalrOperators#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#25)]  
  
## <a name="see-also"></a>Vedere anche

- [Operatori logici e bit per bit (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Operatore And](../../../visual-basic/language-reference/operators/and-operator.md)
- [Operatore IsFalse](../../../visual-basic/language-reference/operators/isfalse-operator.md)
- [Operatori logici e bit per bit in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
