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
ms.openlocfilehash: a5481a9bce01e84ce4f078335c8cd15a747a3c51
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917210"
---
# <a name="is-operator-visual-basic"></a>Operatore Is (Visual Basic)
Confronta due variabili di riferimento a oggetti.  
  
## <a name="syntax"></a>Sintassi  
  
```  
result = object1 Is object2  
```  
  
## <a name="parts"></a>Parti  
 `result`  
 Richiesto. Qualsiasi `Boolean` valore.  
  
 `object1`  
 Richiesto. Qualsiasi `Object` nome.  
  
 `object2`  
 Richiesto. Qualsiasi `Object` nome.  
  
## <a name="remarks"></a>Note  
 L' `Is` operatore determina se due riferimenti a oggetti si riferiscono allo stesso oggetto. Tuttavia, non esegue confronti di valori. Se `object1` ed `True` `result` `result` `False`entrambi fanno riferimento alla stessa istanza dell'oggetto, è; in caso contrario, è. `object2`  
  
 `Is`può essere usato anche con la `TypeOf` parola chiave per creare `TypeOf`un... `Is` espressione, che verifica se una variabile oggetto è compatibile con un tipo di dati.  
  
> [!NOTE]
> La `Is` parola chiave viene inoltre utilizzata nell'oggetto [Select... Istruzione case](../../../visual-basic/language-reference/statements/select-case-statement.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usato `Is` l'operatore per confrontare coppie di riferimenti a oggetti. I risultati vengono assegnati a un `Boolean` valore che indica se i due oggetti sono identici.  
  
 [!code-vb[VbVbalrOperators#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#27)]  
  
 Come illustrato nell'esempio precedente, è possibile usare l' `Is` operatore per testare gli oggetti ad associazione anticipata e ad associazione tardiva.  
  
## <a name="see-also"></a>Vedere anche

- [Operatore TypeOf](../../../visual-basic/language-reference/operators/typeof-operator.md)
- [Operatore IsNot](../../../visual-basic/language-reference/operators/isnot-operator.md)
- [Operatori di confronto in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Operatori ed espressioni](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
