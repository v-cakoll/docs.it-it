---
title: "Procedura: Passare una routine a un'altra routine in Visual Basic"
ms.date: 07/20/2015
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- delegates [Visual Basic], passing procedures
ms.assetid: 5adbba15-5a1d-413f-ab3e-3ff6cc0a4669
ms.openlocfilehash: cf5a8447cbedcd8071da98ac6763ff06eb608199
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54506758"
---
# <a name="how-to-pass-procedures-to-another-procedure-in-visual-basic"></a>Procedura: Passare una routine a un'altra routine in Visual Basic
In questo esempio viene illustrato come usare i delegati per passare una routine a un'altra routine.  
  
 Un delegato è un tipo che è possibile usare come qualsiasi altro tipo in Visual Basic. Il `AddressOf` operatore restituisce un oggetto delegato quando viene applicato a un nome di routine.  
  
 Questo esempio include una procedura con un parametro del delegato che può accettare un riferimento a un'altra routine, ottenuto con la `AddressOf` operatore.  
  
### <a name="create-the-delegate-and-matching-procedures"></a>Creare il delegato e le procedure corrispondente  
  
1.  Creare un delegato denominato `MathOperator`.  
  
     [!code-vb[VbVbalrDelegates#1](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_1.vb)]  
  
2.  Creare una stored procedure denominata `AddNumbers` con parametri e il valore restituito che corrispondono a quelle di `MathOperator`, in modo che le firme corrispondono.  
  
     [!code-vb[VbVbalrDelegates#2](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_2.vb)]  
  
3.  Creare una stored procedure denominata `SubtractNumbers` con una firma corrispondente `MathOperator`.  
  
     [!code-vb[VbVbalrDelegates#3](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_3.vb)]  
  
4.  Creare una routine denominata `DelegateTest` che accetta un delegato come parametro.  
  
     Questa procedura può accettare un riferimento a `AddNumbers` oppure `SubtractNumbers`, in quanto le relative firme corrispondono il `MathOperator` firma.  
  
     [!code-vb[VbVbalrDelegates#4](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_4.vb)]  
  
5.  Creare una stored procedure denominata `Test` che chiama `DelegateTest` una volta con il delegato `AddNumbers` come parametro e nuovamente con il delegato per `SubtractNumbers` come parametro.  
  
     [!code-vb[VbVbalrDelegates#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_5.vb)]  
  
     Quando `Test` viene chiamato, viene innanzitutto visualizzato il risultato del `AddNumbers` che agisce sul `5` e `3`, ovvero 8. Quindi il risultato del `SubtractNumbers` che agisce sul `9` e `3` è visualizzato, che è 6.  
  
## <a name="see-also"></a>Vedere anche
- [Delegati](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [Operatore AddressOf](../../../../visual-basic/language-reference/operators/addressof-operator.md)
- [Istruzione Delegate](../../../../visual-basic/language-reference/statements/delegate-statement.md)
- [Procedura: Richiamare un metodo delegato](../../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
