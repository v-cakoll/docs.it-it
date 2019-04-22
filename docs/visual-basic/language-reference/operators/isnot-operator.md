---
title: Operatore IsNot (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.isnot
helpviewer_keywords:
- IsNot operator [Visual Basic]
ms.assetid: 8dd2bcdb-0166-48a2-9094-60dfb448f36c
ms.openlocfilehash: e07a775eec003a3e488f6909181aed3f742b4b91
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58833516"
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
  
 [!code-vb[VbVbalrOperators#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#29)]  
  
## <a name="see-also"></a>Vedere anche

- [Operatore Is](../../../visual-basic/language-reference/operators/is-operator.md)
- [Operatore TypeOf](../../../visual-basic/language-reference/operators/typeof-operator.md)
- [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Procedura: Verificare se due oggetti sono uguali.](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-test-whether-two-objects-are-the-same.md)
