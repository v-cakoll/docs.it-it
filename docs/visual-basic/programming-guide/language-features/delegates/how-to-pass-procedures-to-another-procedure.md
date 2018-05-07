---
title: "Procedura: passare una routine a un'altra routine in Visual Basic"
ms.date: 07/20/2015
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- delegates [Visual Basic], passing procedures
ms.assetid: 5adbba15-5a1d-413f-ab3e-3ff6cc0a4669
ms.openlocfilehash: c28ac7a640ec863b37bd7407d0273a1918964ac4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-pass-procedures-to-another-procedure-in-visual-basic"></a>Procedura: passare una routine a un'altra routine in Visual Basic
In questo esempio viene illustrato come utilizzare i delegati per passare una routine a un'altra routine.  
  
 Un delegato è un tipo che è possibile utilizzare come qualsiasi altro tipo in Visual Basic. Il `AddressOf` operatore restituisce un oggetto delegato quando applicato a un nome della stored procedure.  
  
 L'esempio include una procedura con un parametro del delegato che può accettare un riferimento a un'altra routine, ottenuto con la `AddressOf` operatore.  
  
### <a name="create-the-delegate-and-matching-procedures"></a>Creare il delegato e le procedure corrispondenti  
  
1.  Crea un delegato denominato `MathOperator`.  
  
     [!code-vb[VbVbalrDelegates#1](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_1.vb)]  
  
2.  Creare una routine denominata `AddNumbers` con parametri e il valore restituito che corrispondono a quelle di `MathOperator`, in modo che le firme corrispondono.  
  
     [!code-vb[VbVbalrDelegates#2](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_2.vb)]  
  
3.  Creare una routine denominata `SubtractNumbers` con una firma corrispondente `MathOperator`.  
  
     [!code-vb[VbVbalrDelegates#3](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_3.vb)]  
  
4.  Creare una routine denominata `DelegateTest` che accetta un delegato come parametro.  
  
     Questa procedura può accettare un riferimento a `AddNumbers` o `SubtractNumbers`, in quanto le relative firme corrispondono il `MathOperator` firma.  
  
     [!code-vb[VbVbalrDelegates#4](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_4.vb)]  
  
5.  Creare una routine denominata `Test` che chiama `DelegateTest` una volta con il delegato per `AddNumbers` come parametro e di nuovo con il delegato per `SubtractNumbers` come parametro.  
  
     [!code-vb[VbVbalrDelegates#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_5.vb)]  
  
     Quando `Test` viene chiamato, viene innanzitutto visualizzato il risultato di `AddNumbers` applicata a `5` e `3`, ovvero 8. Quindi il risultato di `SubtractNumbers` su `9` e `3` viene visualizzato, ovvero 6.  
  
## <a name="see-also"></a>Vedere anche  
 [Delegati](../../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [Operatore AddressOf](../../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [Istruzione Delegate](../../../../visual-basic/language-reference/statements/delegate-statement.md)  
 [Procedura: Richiamare un metodo delegato](../../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
