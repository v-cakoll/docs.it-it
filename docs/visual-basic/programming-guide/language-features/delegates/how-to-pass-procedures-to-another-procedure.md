---
title: "Procedura: Passare una routine a un'altra routine in Visual Basic"
ms.date: 07/20/2015
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- delegates [Visual Basic], passing procedures
ms.assetid: 5adbba15-5a1d-413f-ab3e-3ff6cc0a4669
ms.openlocfilehash: c2305cd18cfaaa67355dfb342f22e39d37ae0e79
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58818475"
---
# <a name="how-to-pass-procedures-to-another-procedure-in-visual-basic"></a>Procedura: Passare una routine a un'altra routine in Visual Basic
In questo esempio viene illustrato come usare i delegati per passare una routine a un'altra routine.  
  
 Un delegato è un tipo che è possibile usare come qualsiasi altro tipo in Visual Basic. Il `AddressOf` operatore restituisce un oggetto delegato quando viene applicato a un nome di routine.  
  
 Questo esempio include una procedura con un parametro del delegato che può accettare un riferimento a un'altra routine, ottenuto con la `AddressOf` operatore.  
  
### <a name="create-the-delegate-and-matching-procedures"></a>Creare il delegato e le procedure corrispondente  
  
1.  Creare un delegato denominato `MathOperator`.  
  
     [!code-vb[VbVbalrDelegates#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#1)]  
  
2.  Creare una stored procedure denominata `AddNumbers` con parametri e il valore restituito che corrispondono a quelle di `MathOperator`, in modo che le firme corrispondono.  
  
     [!code-vb[VbVbalrDelegates#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#2)]  
  
3.  Creare una stored procedure denominata `SubtractNumbers` con una firma corrispondente `MathOperator`.  
  
     [!code-vb[VbVbalrDelegates#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#3)]  
  
4.  Creare una routine denominata `DelegateTest` che accetta un delegato come parametro.  
  
     Questa procedura può accettare un riferimento a `AddNumbers` oppure `SubtractNumbers`, in quanto le relative firme corrispondono il `MathOperator` firma.  
  
     [!code-vb[VbVbalrDelegates#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#4)]  
  
5.  Creare una stored procedure denominata `Test` che chiama `DelegateTest` una volta con il delegato `AddNumbers` come parametro e nuovamente con il delegato per `SubtractNumbers` come parametro.  
  
     [!code-vb[VbVbalrDelegates#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#5)]  
  
     Quando `Test` viene chiamato, viene innanzitutto visualizzato il risultato del `AddNumbers` che agisce sul `5` e `3`, ovvero 8. Quindi il risultato del `SubtractNumbers` che agisce sul `9` e `3` è visualizzato, che è 6.  
  
## <a name="see-also"></a>Vedere anche

- [Delegati](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [Operatore AddressOf](../../../../visual-basic/language-reference/operators/addressof-operator.md)
- [Istruzione Delegate](../../../../visual-basic/language-reference/statements/delegate-statement.md)
- [Procedura: Richiamare un metodo delegato](../../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
