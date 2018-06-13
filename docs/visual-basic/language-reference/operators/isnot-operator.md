---
title: Operatore IsNot (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.isnot
helpviewer_keywords:
- IsNot operator [Visual Basic]
ms.assetid: 8dd2bcdb-0166-48a2-9094-60dfb448f36c
ms.openlocfilehash: babee364d350ca84a8379f675acc4b5c87f98303
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603314"
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
  
 `IsNot` rappresenta l'opposto del `Is` operatore. Il vantaggio di `IsNot` è che è possibile evitare la sintassi difficile con `Not` e `Is`, che può essere difficile da leggere.  
  
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
