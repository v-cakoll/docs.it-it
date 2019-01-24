---
title: Operatore IsNot (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.isnot
helpviewer_keywords:
- IsNot operator [Visual Basic]
ms.assetid: 8dd2bcdb-0166-48a2-9094-60dfb448f36c
ms.openlocfilehash: ffafff915af8a94e9bc135246064e4c049d41838
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54596462"
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
 Il `IsNot` operatore determina se due riferimenti a oggetti si riferiscono a oggetti diversi. Tuttavia, non esegue confronti di valore. Se `object1` e `object2` entrambi la stessa istanza di oggetto, si intende `result` viene `False`; in caso contrario, `result` è `True`.  
  
 `IsNot` è l'opposto del `Is` operatore. Il vantaggio `IsNot` è che è possibile evitare sintassi difficile `Not` e `Is`, che può essere difficile da leggere.  
  
 È possibile usare la `Is` e `IsNot` operatori per testare gli oggetti ad associazione anticipata e tardiva.  
  
> [!NOTE]
>  Il `IsNot` operatore non può essere utilizzato per confrontare espressioni restituite dal `TypeOf` operatore. In alternativa, è necessario usare il `Not` e `Is` operatori.  
  
## <a name="example"></a>Esempio  
 Esempio di codice seguente usa sia la `Is` operatore e `IsNot` operatore per eseguire lo stesso confronto.  
  
 [!code-vb[VbVbalrOperators#29](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/isnot-operator_1.vb)]  
  
## <a name="see-also"></a>Vedere anche
- [Operatore Is](../../../visual-basic/language-reference/operators/is-operator.md)
- [Operatore TypeOf](../../../visual-basic/language-reference/operators/typeof-operator.md)
- [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Procedura: Verificare se due oggetti sono uguali.](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-test-whether-two-objects-are-the-same.md)
