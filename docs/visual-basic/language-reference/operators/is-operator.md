---
title: Operatore Is (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.is
helpviewer_keywords:
- comparison operators [Visual Basic]
- equivalent objects
- TypeOf...Is expression
- Is operator [Visual Basic]
ms.assetid: 8045a6c8-2a83-45b6-ad47-d09a704c656d
ms.openlocfilehash: 8beca1dc8788514224f70cacc5b8ede0974f5230
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33601950"
---
# <a name="is-operator-visual-basic"></a>Operatore Is (Visual Basic)
Confronta due variabili di riferimento di oggetto.  
  
## <a name="syntax"></a>Sintassi  
  
```  
result = object1 Is object2  
```  
  
## <a name="parts"></a>Parti  
 `result`  
 Obbligatorio. Qualsiasi `Boolean` valore.  
  
 `object1`  
 Obbligatorio. Qualsiasi `Object` nome.  
  
 `object2`  
 Obbligatorio. Qualsiasi `Object` nome.  
  
## <a name="remarks"></a>Note  
 Il `Is` operatore determina se due riferimenti a oggetti si riferiscono allo stesso oggetto. Tuttavia, non esegue i confronti di valore. Se `object1` e `object2` si riferiscono entrambi alla stessa istanza di oggetto, `result` è `True`; in caso contrario, `result` è `False`.  
  
 `Is` può anche essere utilizzato con il `TypeOf` (parola chiave) per rendere un `TypeOf`... `Is` espressione, che verifica se una variabile oggetto è compatibile con un tipo di dati.  
  
> [!NOTE]
>  Il `Is` (parola chiave) viene usato anche nel [Seleziona... Istruzione case](../../../visual-basic/language-reference/statements/select-case-statement.md).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il `Is` operatore per confrontare le coppie di riferimenti agli oggetti. I risultati vengono assegnati a un `Boolean` valore che indica se due oggetti sono identici.  
  
 [!code-vb[VbVbalrOperators#27](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/is-operator_1.vb)]  
  
 Come illustrato nell'esempio precedente, è possibile utilizzare il `Is` operatore per testare sia con associazione anticipata e tardiva oggetti.  
  
## <a name="see-also"></a>Vedere anche  
 [Operatore TypeOf](../../../visual-basic/language-reference/operators/typeof-operator.md)  
 [Operatore IsNot](../../../visual-basic/language-reference/operators/isnot-operator.md)  
 [Operatori di confronto in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)  
 [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Operatori ed espressioni](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
