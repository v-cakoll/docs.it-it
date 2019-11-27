---
title: Operatore IsTrue
ms.date: 07/20/2015
f1_keywords:
- vb.istrue
helpviewer_keywords:
- IsTrue operator [Visual Basic]
- OrElse operator [Visual Basic]
ms.assetid: b6cec0f2-61b1-4331-a7f0-4d07ee3179d6
ms.openlocfilehash: 4b863eed8406a10b9a44d7139f8659ac5cb758ad
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349507"
---
# <a name="istrue-operator-visual-basic"></a>Operatore IsTrue (Visual Basic)
Determina se un'espressione viene `True`.  
  
 Non è possibile chiamare `IsTrue` in modo esplicito nel codice, ma il compilatore Visual Basic può usarlo per generare codice da `OrElse` clausole. Se si definisce una classe o una struttura e quindi si usa una variabile di quel tipo in una clausola `OrElse`, è necessario definire `IsTrue` sulla classe o sulla struttura.  
  
 Il compilatore considera gli operatori `IsTrue` e `IsFalse` come *coppia corrispondente*. Ciò significa che se si definisce uno di essi, è necessario definire anche l'altro.  
  
## <a name="compiler-use-of-istrue"></a>Uso del compilatore di IsTrue  
 Una volta definita una classe o una struttura, è possibile usare una variabile di quel tipo in un'istruzione `For`, `If`, `Else If`o `While` oppure in una clausola `When`. In tal caso, il compilatore richiede un operatore che converte il tipo in un valore `Boolean` in modo che possa testare una condizione. Cerca un operatore appropriato nell'ordine seguente:  
  
1. Un operatore di conversione verso un tipo di dati più ampio dalla classe o dalla struttura `Boolean`.  
  
2. Un operatore di conversione verso un tipo di dati più ampio dalla classe o dalla struttura `Boolean?`.  
  
3. Operatore `IsTrue` sulla classe o sulla struttura.  
  
4. Una conversione verso un tipo di `Boolean?` più piccolo che non comporta una conversione da `Boolean` a `Boolean?`.  
  
5. Operatore di conversione verso un tipo di dati più piccolo dalla classe o dalla struttura `Boolean`.  
  
 Se non è stata definita alcuna conversione a `Boolean` o a un operatore `IsTrue`, il compilatore segnala un errore.  
  
> [!NOTE]
> L'operatore `IsTrue` può essere sottoposto a *Overload*, il che significa che una classe o una struttura può ridefinire il comportamento quando il relativo operando ha il tipo della classe o della struttura. Se il codice usa questo operatore su una classe o una struttura di questo tipo, assicurarsi di comprendere il comportamento ridefinito. Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice seguente viene definita la struttura di una struttura che include definizioni per gli operatori `IsFalse` e `IsTrue`.  
  
 [!code-vb[VbVbalrOperators#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#28)]  
  
## <a name="see-also"></a>Vedere anche

- [Operatore IsFalse](../../../visual-basic/language-reference/operators/isfalse-operator.md)
- [Procedura: Definire un operatore](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [Operatore OrElse](../../../visual-basic/language-reference/operators/orelse-operator.md)
