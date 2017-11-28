---
title: Operatore IsNot (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.isnot
helpviewer_keywords: IsNot operator [Visual Basic]
ms.assetid: 8dd2bcdb-0166-48a2-9094-60dfb448f36c
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 969fdebdf15a1f779075c58616ccd16c64976a35
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="isnot-operator-visual-basic"></a>Operatore IsNot (Visual Basic)
Confronta due variabili di riferimento di oggetto.  
  
## <a name="syntax"></a>Sintassi  
  
```  
result = object1 IsNot object2  
```  
  
## <a name="parts"></a>Parti  
 `result`  
 Obbligatorio. Valore `Boolean`.  
  
 `object1`  
 Obbligatorio. Qualsiasi `Object` variabile o espressione.  
  
 `object2`  
 Obbligatorio. Qualsiasi `Object` variabile o espressione.  
  
## <a name="remarks"></a>Note  
 Il `IsNot` operatore determina se due riferimenti a oggetti fanno riferimento a oggetti diversi. Tuttavia, non esegue i confronti di valore. Se `object1` e `object2` si riferiscono entrambi alla stessa istanza di oggetto, `result` è `False`; in caso contrario, `result` è `True`.  
  
 `IsNot`è l'opposto del `Is` operatore. Il vantaggio di `IsNot` è che è possibile evitare la sintassi difficile con `Not` e `Is`, che può essere difficile da leggere.  
  
 È possibile utilizzare il `Is` e `IsNot` operatori per testare gli oggetti sia con associazione anticipata e tardiva.  
  
> [!NOTE]
>  Il `IsNot` operatore non può essere utilizzato per confrontare espressioni restituite dal `TypeOf` operatore. In alternativa, è necessario utilizzare il `Not` e `Is` operatori.  
  
## <a name="example"></a>Esempio  
 Esempio di codice seguente utilizza sia il `Is` operatore e `IsNot` operatore per eseguire lo stesso confronto.  
  
 [!code-vb[VbVbalrOperators#29](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/isnot-operator_1.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Operatore Is](../../../visual-basic/language-reference/operators/is-operator.md)  
 [Operatore TypeOf](../../../visual-basic/language-reference/operators/typeof-operator.md)  
 [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Procedura: Determinare se due oggetti sono uguali](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-test-whether-two-objects-are-the-same.md)
