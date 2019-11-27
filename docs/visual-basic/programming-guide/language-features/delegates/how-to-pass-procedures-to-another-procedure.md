---
title: "Procedura: passare routine a un'altra routine"
ms.date: 07/20/2015
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- delegates [Visual Basic], passing procedures
ms.assetid: 5adbba15-5a1d-413f-ab3e-3ff6cc0a4669
ms.openlocfilehash: 300489935ce54d78b989d09211a7f6ba95c2f514
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345252"
---
# <a name="how-to-pass-procedures-to-another-procedure-in-visual-basic"></a>Procedura: passare una routine a un'altra routine in Visual Basic
Questo esempio illustra come usare i delegati per passare una routine a un'altra routine.  
  
 Un delegato è un tipo che può essere usato come qualsiasi altro tipo in Visual Basic. L'operatore `AddressOf` restituisce un oggetto delegato quando viene applicato al nome di una stored procedure.  
  
 Questo esempio include una routine con un parametro delegate che può assumere un riferimento a un'altra routine, ottenuta con l'operatore `AddressOf`.  
  
### <a name="create-the-delegate-and-matching-procedures"></a>Creare il delegato e le procedure di corrispondenza  
  
1. Creare un delegato denominato `MathOperator`.  
  
     [!code-vb[VbVbalrDelegates#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#1)]  
  
2. Creare una routine denominata `AddNumbers` con i parametri e il valore restituito corrispondenti a quelli di `MathOperator`, in modo che le firme corrispondano.  
  
     [!code-vb[VbVbalrDelegates#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#2)]  
  
3. Creare una routine denominata `SubtractNumbers` con una firma corrispondente `MathOperator`.  
  
     [!code-vb[VbVbalrDelegates#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#3)]  
  
4. Creare una routine denominata `DelegateTest` che accetta un delegato come parametro.  
  
     Questa procedura può accettare un riferimento a `AddNumbers` o `SubtractNumbers`, perché le relative firme corrispondono alla firma di `MathOperator`.  
  
     [!code-vb[VbVbalrDelegates#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#4)]  
  
5. Creare una routine denominata `Test` che chiama `DelegateTest` una volta con il delegato per `AddNumbers` come parametro e di nuovo con il delegato per `SubtractNumbers` come parametro.  
  
     [!code-vb[VbVbalrDelegates#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#5)]  
  
     Quando viene chiamato `Test`, viene prima visualizzato il risultato di `AddNumbers` che agisce su `5` e `3`, ovvero 8. Viene quindi visualizzato il risultato di `SubtractNumbers` che agisce su `9` e `3`, che è 6.  
  
## <a name="see-also"></a>Vedere anche

- [Delegati](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [Operatore AddressOf](../../../../visual-basic/language-reference/operators/addressof-operator.md)
- [Istruzione Delegate](../../../../visual-basic/language-reference/statements/delegate-statement.md)
- [Procedura: Richiamare un metodo delegato](../../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
