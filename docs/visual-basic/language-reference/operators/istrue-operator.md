---
title: Operatore IsTrue
ms.date: 07/20/2015
f1_keywords:
- vb.istrue
helpviewer_keywords:
- IsTrue operator [Visual Basic]
- OrElse operator [Visual Basic]
ms.assetid: b6cec0f2-61b1-4331-a7f0-4d07ee3179d6
ms.openlocfilehash: bc129d3a3aec76285d5ea8fb727fc72c3064c9cf
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84370648"
---
# <a name="istrue-operator-visual-basic"></a>Operatore IsTrue (Visual Basic)
Determina se un'espressione è `True` .  
  
 Non è possibile chiamare `IsTrue` in modo esplicito nel codice, ma il compilatore Visual Basic può usarlo per generare codice da `OrElse` clausole. Se si definisce una classe o una struttura e quindi si usa una variabile di quel tipo in una `OrElse` clausola, è necessario definire `IsTrue` su tale classe o struttura.  
  
 Il compilatore considera gli `IsTrue` `IsFalse` operatori e come una *coppia corrispondente*. Ciò significa che se si definisce uno di essi, è necessario definire anche l'altro.  
  
## <a name="compiler-use-of-istrue"></a>Uso del compilatore di IsTrue  
 Una volta definita una classe o una struttura, è possibile utilizzare una variabile di quel tipo in un' `For` `If` istruzione,, `Else If` o o `While` in una `When` clausola. In tal caso, il compilatore richiede un operatore che converte il tipo in un `Boolean` valore in modo che possa testare una condizione. Cerca un operatore appropriato nell'ordine seguente:  
  
1. Un operatore di conversione verso un tipo di dati più ampio dalla classe o dalla struttura a `Boolean` .  
  
2. Un operatore di conversione verso un tipo di dati più ampio dalla classe o dalla struttura a `Boolean?` .  
  
3. `IsTrue`Operatore sulla classe o sulla struttura.  
  
4. Una conversione verso un tipo di caratteri più piccolo `Boolean?` non comporta una conversione da `Boolean` a `Boolean?` .  
  
5. Operatore di conversione verso un tipo di dati più piccolo dalla classe o dalla struttura a `Boolean` .  
  
 Se non è stata definita alcuna conversione a `Boolean` o a un `IsTrue` operatore, il compilatore segnala un errore.  
  
> [!NOTE]
> L' `IsTrue` operatore può essere sottoposto a *Overload*, il che significa che una classe o una struttura può ridefinire il comportamento quando il relativo operando ha il tipo della classe o della struttura. Se il codice usa questo operatore su una classe o una struttura di questo tipo, assicurarsi di comprendere il comportamento ridefinito. Per altre informazioni, vedere [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice seguente viene definita la struttura di una struttura che include definizioni per gli `IsFalse` `IsTrue` operatori e.  
  
 [!code-vb[VbVbalrOperators#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#28)]  
  
## <a name="see-also"></a>Vedere anche

- [Operatore IsFalse](isfalse-operator.md)
- [Procedura: definire un operatore](../../programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [Operatore OrElse](orelse-operator.md)
