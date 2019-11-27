---
title: Operatore Is
ms.date: 07/20/2015
f1_keywords:
- vb.is
helpviewer_keywords:
- comparison operators [Visual Basic]
- equivalent objects
- TypeOf...Is expression
- Is operator [Visual Basic]
ms.assetid: 8045a6c8-2a83-45b6-ad47-d09a704c656d
ms.openlocfilehash: 52fbb39ab0a36c8b947b78f464fad26be05ce204
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349539"
---
# <a name="is-operator-visual-basic"></a>Operatore Is (Visual Basic)
Confronta due variabili di riferimento a oggetti.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
result = object1 Is object2  
```  
  
## <a name="parts"></a>Parti  
 `result`  
 Obbligatoria. Qualsiasi valore `Boolean`.  
  
 `object1`  
 Obbligatoria. Qualsiasi nome del `Object`.  
  
 `object2`  
 Obbligatoria. Qualsiasi nome del `Object`.  
  
## <a name="remarks"></a>Note  
 L'operatore `Is` determina se due riferimenti a oggetti si riferiscono allo stesso oggetto. Tuttavia, non esegue confronti di valori. Se `object1` e `object2` entrambi fanno riferimento alla stessa istanza dell'oggetto, `result` è `True`; in caso contrario, `result` viene `False`.  
  
 `Is` possibile utilizzare anche con la parola chiave `TypeOf` per creare un'espressione `TypeOf`...`Is`, che verifica se una variabile oggetto è compatibile con un tipo di dati.  
  
> [!NOTE]
> La parola chiave `Is` viene inoltre utilizzata nell'oggetto [Select... Istruzione case](../../../visual-basic/language-reference/statements/select-case-statement.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usato l'operatore `Is` per confrontare coppie di riferimenti a oggetti. I risultati vengono assegnati a un valore `Boolean` che indica se i due oggetti sono identici.  
  
 [!code-vb[VbVbalrOperators#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#27)]  
  
 Come illustrato nell'esempio precedente, è possibile usare l'operatore `Is` per testare gli oggetti ad associazione anticipata e ad associazione tardiva.  
  
## <a name="see-also"></a>Vedere anche

- [Operatore TypeOf](../../../visual-basic/language-reference/operators/typeof-operator.md)
- [Operatore IsNot](../../../visual-basic/language-reference/operators/isnot-operator.md)
- [Operatori di confronto in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Operatori ed espressioni](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
