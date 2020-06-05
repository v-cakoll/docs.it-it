---
title: "Procedura: Passare una routine a un'altra routine"
ms.date: 07/20/2015
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- delegates [Visual Basic], passing procedures
ms.assetid: 5adbba15-5a1d-413f-ab3e-3ff6cc0a4669
ms.openlocfilehash: 36f623068372614ae034a8a7b31bffb7496f98b1
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410695"
---
# <a name="how-to-pass-procedures-to-another-procedure-in-visual-basic"></a>Procedura: passare una routine a un'altra routine in Visual Basic
Questo esempio illustra come usare i delegati per passare una routine a un'altra routine.  
  
 Un delegato è un tipo che può essere usato come qualsiasi altro tipo in Visual Basic. L' `AddressOf` operatore restituisce un oggetto delegato quando viene applicato al nome di una stored procedure.  
  
 Questo esempio include una routine con un parametro delegate che può assumere un riferimento a un'altra routine, ottenuta con l' `AddressOf` operatore.  
  
### <a name="create-the-delegate-and-matching-procedures"></a>Creare il delegato e le procedure di corrispondenza  
  
1. Creare un delegato denominato `MathOperator` .  
  
     [!code-vb[VbVbalrDelegates#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#1)]  
  
2. Creare una routine denominata `AddNumbers` con i parametri e il valore restituito corrispondenti a quelli di `MathOperator` , in modo che le firme corrispondano.  
  
     [!code-vb[VbVbalrDelegates#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#2)]  
  
3. Creare una routine denominata `SubtractNumbers` con una firma corrispondente a `MathOperator` .  
  
     [!code-vb[VbVbalrDelegates#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#3)]  
  
4. Creare una stored procedure denominata `DelegateTest` che accetta un delegato come parametro.  
  
     Questa procedura può accettare un riferimento a `AddNumbers` o `SubtractNumbers` , perché le relative firme corrispondono alla `MathOperator` firma.  
  
     [!code-vb[VbVbalrDelegates#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#4)]  
  
5. Creare una routine denominata `Test` che chiama `DelegateTest` una volta con il delegato per `AddNumbers` come parametro e di nuovo con il delegato per `SubtractNumbers` come parametro.  
  
     [!code-vb[VbVbalrDelegates#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#5)]  
  
     Quando `Test` viene chiamato, viene prima visualizzato il risultato dell' `AddNumbers` azione su `5` e `3` , che è 8. Viene quindi visualizzato il risultato dell' `SubtractNumbers` azione su `9` e `3` , che è 6.  
  
## <a name="see-also"></a>Vedere anche

- [Delegati](index.md)
- [Operatore AddressOf](../../../language-reference/operators/addressof-operator.md)
- [Istruzione Delegate](../../../language-reference/statements/delegate-statement.md)
- [Procedura: richiamare un metodo delegato](how-to-invoke-a-delegate-method.md)
