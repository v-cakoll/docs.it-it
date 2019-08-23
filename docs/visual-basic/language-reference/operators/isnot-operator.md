---
title: Operatore IsNot (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.isnot
helpviewer_keywords:
- IsNot operator [Visual Basic]
ms.assetid: 8dd2bcdb-0166-48a2-9094-60dfb448f36c
ms.openlocfilehash: 0a83b48e5e415bd6ca0c777cef6d34f7127691b5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966932"
---
# <a name="isnot-operator-visual-basic"></a>Operatore IsNot (Visual Basic)
Confronta due variabili di riferimento a oggetti.  
  
## <a name="syntax"></a>Sintassi  
  
```  
result = object1 IsNot object2  
```  
  
## <a name="parts"></a>Parti  
 `result`  
 Richiesto. Valore `Boolean`.  
  
 `object1`  
 Richiesto. Qualsiasi `Object` variabile o espressione.  
  
 `object2`  
 Richiesto. Qualsiasi `Object` variabile o espressione.  
  
## <a name="remarks"></a>Note  
 L' `IsNot` operatore determina se due riferimenti a oggetti si riferiscono a oggetti diversi. Tuttavia, non esegue confronti di valori. Se `object1` ed `False` `result` `result` `True`entrambi fanno riferimento alla stessa istanza dell'oggetto, è; in caso contrario, è. `object2`  
  
 `IsNot`è l'opposto dell' `Is` operatore. Il vantaggio di `IsNot` è che è possibile evitare la sintassi scomoda `Not` con `Is`e, che può essere difficile da leggere.  
  
 È possibile utilizzare gli `Is` operatori `IsNot` e per testare gli oggetti ad associazione anticipata e ad associazione tardiva.  
  
> [!NOTE]
> Non `IsNot` è possibile usare l'operatore per confrontare le espressioni restituite `TypeOf` dall'operatore. È invece necessario usare gli `Not` operatori e. `Is`  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice seguente vengono usati `Is` sia l'operatore `IsNot` che l'operatore per eseguire lo stesso confronto.  
  
 [!code-vb[VbVbalrOperators#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#29)]  
  
## <a name="see-also"></a>Vedere anche

- [Operatore Is](../../../visual-basic/language-reference/operators/is-operator.md)
- [Operatore TypeOf](../../../visual-basic/language-reference/operators/typeof-operator.md)
- [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Procedura: Verificare se due oggetti sono uguali](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-test-whether-two-objects-are-the-same.md)
