---
title: Operatore IsTrue (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.istrue
helpviewer_keywords:
- IsTrue operator [Visual Basic]
- OrElse operator [Visual Basic]
ms.assetid: b6cec0f2-61b1-4331-a7f0-4d07ee3179d6
ms.openlocfilehash: 1152f4b512a85ae183f8fc8d476b69685e2926ef
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966924"
---
# <a name="istrue-operator-visual-basic"></a>Operatore IsTrue (Visual Basic)
Determina se un'espressione è `True`.  
  
 Non è possibile `IsTrue` chiamare in modo esplicito nel codice, ma il compilatore Visual Basic può usarlo per generare `OrElse` codice da clausole. Se si definisce una classe o una struttura e quindi si usa una variabile di quel tipo `OrElse` in una clausola, è `IsTrue` necessario definire su tale classe o struttura.  
  
 Il compilatore considera gli `IsTrue` operatori `IsFalse` e come una *coppia corrispondente*. Ciò significa che se si definisce uno di essi, è necessario definire anche l'altro.  
  
## <a name="compiler-use-of-istrue"></a>Uso del compilatore di IsTrue  
 Una volta definita una classe o una struttura, è possibile utilizzare una variabile di quel tipo in un' `For`istruzione `If`, `Else If`, o `While` o in una `When` clausola. In tal caso, il compilatore richiede un operatore che converte il tipo in un `Boolean` valore in modo che possa testare una condizione. Cerca un operatore appropriato nell'ordine seguente:  
  
1. Un operatore di conversione verso un tipo di dati più ampio `Boolean`dalla classe o dalla struttura a.  
  
2. Un operatore di conversione verso un tipo di dati più ampio `Boolean?`dalla classe o dalla struttura a.  
  
3. `IsTrue` Operatore sulla classe o sulla struttura.  
  
4. Una conversione verso un tipo `Boolean?` di caratteri più piccolo non comporta una `Boolean` conversione `Boolean?`da a.  
  
5. Operatore di conversione verso un tipo di dati più piccolo dalla `Boolean`classe o dalla struttura a.  
  
 Se non è stata definita alcuna conversione a `Boolean` o a `IsTrue` un operatore, il compilatore segnala un errore.  
  
> [!NOTE]
> L' `IsTrue` operatore può essere sottoposto a *Overload*, il che significa che una classe o una struttura può ridefinire il comportamento quando il relativo operando ha il tipo della classe o della struttura. Se il codice usa questo operatore su una classe o una struttura di questo tipo, assicurarsi di comprendere il comportamento ridefinito. Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice seguente viene definita la struttura di una struttura che include definizioni `IsFalse` per `IsTrue` gli operatori e.  
  
 [!code-vb[VbVbalrOperators#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#28)]  
  
## <a name="see-also"></a>Vedere anche

- [Operatore IsFalse](../../../visual-basic/language-reference/operators/isfalse-operator.md)
- [Procedura: Definire un operatore](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [Operatore OrElse](../../../visual-basic/language-reference/operators/orelse-operator.md)
