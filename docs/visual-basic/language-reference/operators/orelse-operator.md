---
title: Operatore OrElse
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
ms.openlocfilehash: 361de44711c3b41411f2fa1dd81a3dd8db6b01e6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348238"
---
# <a name="orelse-operator-visual-basic"></a>Operatore OrElse (Visual Basic)
Esegue una disgiunzione logica inclusiva di corto circuito su due espressioni.  
  
## <a name="syntax"></a>Sintassi  
  
```vb
result = expression1 OrElse expression2  
```  
  
## <a name="parts"></a>Parti  
 `result`  
 Obbligatoria. Qualsiasi espressione `Boolean` .  
  
 `expression1`  
 Obbligatoria. Qualsiasi espressione `Boolean` .  
  
 `expression2`  
 Obbligatoria. Qualsiasi espressione `Boolean` .  
  
## <a name="remarks"></a>Osservazioni  
 Un'operazione logica viene detta *corto circuito* se il codice compilato può ignorare la valutazione di un'espressione a seconda del risultato di un'altra espressione. Se il risultato della prima espressione valutata determina il risultato finale dell'operazione, non è necessario valutare la seconda espressione, perché non è in grado di modificare il risultato finale. Il cortocircuito può migliorare le prestazioni se l'espressione bypassata è complessa o se implica chiamate di routine.  
  
 Se una o entrambe le espressioni restituiscono `True`, `result` è `True`. Nella tabella seguente viene illustrato il modo in cui viene determinato `result`.  
  
|Se `expression1` è|E `expression2` è|Il valore di `result` è|  
|-------------------------|--------------------------|------------------------------|  
|`True`|(non valutato)|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
## <a name="data-types"></a>Tipi di dati  
 L'operatore `OrElse` viene definito solo per il [tipo di dati Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md). Visual Basic converte ogni operando come necessario per `Boolean` prima di valutare l'espressione. Se il risultato viene assegnato a un tipo numerico, Visual Basic lo converte da `Boolean` a tale tipo, in modo che `False` diventi `0` e `True` diventi `-1`.
Per altre informazioni, vedere [conversioni di tipi booleani](../data-types/boolean-data-type.md#type-conversions).
  
## <a name="overloading"></a>Overload  
 L' [operatore OR](../../../visual-basic/language-reference/operators/or-operator.md) e l' [operatore IsTrue](../../../visual-basic/language-reference/operators/istrue-operator.md) possono essere sottoposto a *Overload*, il che significa che una classe o una struttura può ridefinire il comportamento quando un operando ha il tipo della classe o della struttura. L'overload degli operatori `Or` e `IsTrue` influiscono sul comportamento dell'operatore `OrElse`. Se il codice USA `OrElse` su una classe o una struttura che esegue l'overload di `Or` e `IsTrue`, assicurarsi di comprendere il comportamento ridefinito. Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usato l'operatore `OrElse` per eseguire la disgiunzione logica di due espressioni. Il risultato è un valore `Boolean` che indica se una delle due espressioni è true. Se la prima espressione è `True`, la seconda non viene valutata.  
  
 [!code-vb[VbVbalrOperators#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#37)]  
  
 Nell'esempio precedente vengono restituiti i risultati di `True`, `True`e `False` rispettivamente. Nel calcolo di `firstCheck`la seconda espressione non viene valutata perché il primo è già `True`. Tuttavia, la seconda espressione viene valutata nel calcolo del `secondCheck`.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrata un'istruzione `If`...`Then` contenente due chiamate di procedura. Se la prima chiamata restituisce `True`, la seconda procedura non viene chiamata. Questo potrebbe produrre risultati imprevisti se la seconda procedura esegue attività importanti che devono essere sempre eseguite quando viene eseguita questa sezione del codice.  
  
 [!code-vb[VbVbalrOperators#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#38)]  
  
## <a name="see-also"></a>Vedere anche

- [Operatori logici/bit per bit (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Operatore Or](../../../visual-basic/language-reference/operators/or-operator.md)
- [Operatore IsTrue](../../../visual-basic/language-reference/operators/istrue-operator.md)
- [Operatori logici e bit per bit in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
