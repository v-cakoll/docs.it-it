---
title: Operatore IsTrue (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.istrue
helpviewer_keywords:
- IsTrue operator [Visual Basic]
- OrElse operator [Visual Basic]
ms.assetid: b6cec0f2-61b1-4331-a7f0-4d07ee3179d6
ms.openlocfilehash: bf81384b0cecfd1ee3d438e4463949381279a181
ms.sourcegitcommit: fe02afbc39e78afd78cc6050e4a9c12a75f579f8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/30/2018
ms.locfileid: "43254879"
---
# <a name="istrue-operator-visual-basic"></a>Operatore IsTrue (Visual Basic)
Determina se un'espressione è `True`.  
  
 Non è possibile chiamare `IsTrue` in modo esplicito nel codice, ma Visual Basic compilatore può utilizzarlo per generare codice da `OrElse` clausole. Se si definisce una classe o struttura e quindi usare una variabile di quel tipo in un `OrElse` clausola, è necessario definire `IsTrue` in quella classe o struttura.  
  
 Il compilatore considera il `IsTrue` e `IsFalse` operatori come una *coppia associata*. Ciò significa che se si definisce uno di essi, è necessario anche definire un'altra.  
  
## <a name="compiler-use-of-istrue"></a>Uso del compilatore di IsTrue  
 Dopo aver definito una classe o struttura, è possibile usare una variabile di quel tipo in un `For`, `If`, `Else If`, o `While` istruzione o in un `When` clausola. In questo caso, il compilatore richiede un operatore che converta il tipo in un `Boolean` valore in modo che è possibile testare una condizione. La ricerca di un operatore appropriato nell'ordine seguente:  
  
1.  Un operatore di conversione widening nella classe o struttura `Boolean`.  
  
2.  Un operatore di conversione widening nella classe o struttura `Boolean?`.  
  
3.  Il `IsTrue` operatore sulla classe o struttura.  
  
4.  Conversioni verso `Boolean?` che non comporta una conversione da `Boolean` a `Boolean?`.  
  
5.  Un operatore di conversione narrowing nella classe o struttura `Boolean`.  
  
 Se non è stata definita alcuna conversione a `Boolean` o un `IsTrue` (operatore), il compilatore segnalerà un errore.  
  
> [!NOTE]
>  Il `IsTrue` operatore può essere *sottoposto a overload*, il che significa che una classe o struttura può ridefinire il comportamento quando l'operando ha il tipo di quella classe o struttura. Se il codice Usa l'operatore su una classe o struttura, assicurarsi di che comprendere il comportamento ridefinito. Per altre informazioni, vedere [routine di operatore](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 Esempio di codice seguente definisce la struttura di una struttura che include le definizioni per il `IsFalse` e `IsTrue` operatori.  
  
 [!code-vb[VbVbalrOperators#28](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/istrue-operator_1.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Operatore IsFalse](../../../visual-basic/language-reference/operators/isfalse-operator.md)  
 [Procedura: Definire un operatore](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [Operatore OrElse](../../../visual-basic/language-reference/operators/orelse-operator.md)
