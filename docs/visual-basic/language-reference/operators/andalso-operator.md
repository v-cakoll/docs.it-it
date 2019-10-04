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
ms.openlocfilehash: a52f598c8a7c7a79b0f2436f1add7b3eb5d5261b
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/03/2019
ms.locfileid: "71835224"
---
# <a name="andalso-operator-visual-basic"></a>Operatore AndAlso (Visual Basic)
Esegue una congiunzione logica di corto circuito su due espressioni.  
  
## <a name="syntax"></a>Sintassi  
  
```vb
result = expression1 AndAlso expression2  
```  
  
## <a name="parts"></a>Parti  
  
|Nome|Definizione|  
|---|---|  
|`result`|Obbligatorio. Qualsiasi espressione `Boolean` . Il risultato è il risultato `Boolean` del confronto delle due espressioni.|  
|`expression1`|Obbligatorio. Qualsiasi espressione `Boolean` .|  
|`expression2`|Obbligatorio. Qualsiasi espressione `Boolean` .|  
  
## <a name="remarks"></a>Note  
 Un'operazione logica viene detta *corto circuito* se il codice compilato può ignorare la valutazione di un'espressione a seconda del risultato di un'altra espressione. Se il risultato della prima espressione valutata determina il risultato finale dell'operazione, non è necessario valutare la seconda espressione, perché non è in grado di modificare il risultato finale. Il cortocircuito può migliorare le prestazioni se l'espressione bypassata è complessa o se implica chiamate di routine.  
  
 Se entrambe le espressioni restituiscono `True`, `result` è `True`. Nella tabella seguente viene illustrato il modo in cui viene determinato `result`.  
  
|Se `expression1` è|E `expression2` è|Il valore di `result` è|  
|---|---|---|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|(non valutato)|`False`|  
  
## <a name="data-types"></a>Tipi di dati  
 L'operatore `AndAlso` viene definito solo per il [tipo di dati Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md). Visual Basic converte ogni operando nel modo necessario per `Boolean` prima di valutare l'espressione. Se il risultato viene assegnato a un tipo numerico, Visual Basic lo converte da `Boolean` a tale tipo, in modo che `False` diventi `0` e `True` diventi `-1`.
Per altre informazioni, vedere [conversioni di tipi booleani](../data-types/boolean-data-type.md#type-conversions).
  
## <a name="overloading"></a>Overload  
 È possibile eseguire l' *Overload*dell' [operatore and](../../../visual-basic/language-reference/operators/and-operator.md) e dell' [operatore false](../../../visual-basic/language-reference/operators/isfalse-operator.md) , il che significa che una classe o una struttura può ridefinire il comportamento quando un operando ha il tipo della classe o della struttura. L'overload degli operatori `And` e `IsFalse` influiscono sul comportamento dell'operatore `AndAlso`. Se il codice USA `AndAlso` su una classe o una struttura che esegue l'overload di `And` e `IsFalse`, assicurarsi di comprendere il comportamento ridefinito. Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usato l'operatore `AndAlso` per eseguire una congiunzione logica di due espressioni. Il risultato è un valore `Boolean` che indica se l'intera espressione conjointa è true. Se la prima espressione è `False`, la seconda non viene valutata.  
  
 [!code-vb[VbVbalrOperators#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#24)]  
  
 Nell'esempio precedente vengono prodotti rispettivamente i risultati `True`, `False` e `False`. Nel calcolo di `secondCheck`, la seconda espressione non viene valutata perché il primo è già `False`. Tuttavia, la seconda espressione viene valutata nel calcolo di `thirdCheck`.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrata una procedura `Function` che cerca un valore specificato tra gli elementi di una matrice. Se la matrice è vuota o se la lunghezza della matrice è stata superata, l'istruzione `While` non esegue il test dell'elemento della matrice rispetto al valore di ricerca.  
  
 [!code-vb[VbVbalrOperators#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#25)]  
  
## <a name="see-also"></a>Vedere anche

- [Operatori logici/bit per bit (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Operatore And](../../../visual-basic/language-reference/operators/and-operator.md)
- [Operatore IsFalse](../../../visual-basic/language-reference/operators/isfalse-operator.md)
- [Operatori logici e bit per bit in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
