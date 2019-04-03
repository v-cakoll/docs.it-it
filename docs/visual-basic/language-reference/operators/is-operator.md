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
ms.openlocfilehash: a59ff4c956724c614342f0ee4c0622a67f1c25e7
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58817071"
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
 Il `Is` operatore determina se due riferimenti a oggetti si riferiscono allo stesso oggetto. Tuttavia, non esegue confronti di valore. Se `object1` e `object2` entrambi la stessa istanza di oggetto, si intende `result` viene `True`; in caso contrario, `result` è `False`.  
  
 `Is` è anche utilizzabile con il `TypeOf` parola chiave per rendere un `TypeOf`... `Is` espressione, che verifica se una variabile oggetto è compatibile con un tipo di dati.  
  
> [!NOTE]
>  Il `Is` parola chiave viene usata anche nel [Seleziona... Istruzione case](../../../visual-basic/language-reference/statements/select-case-statement.md).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il `Is` operatore per confrontare coppie di riferimenti a oggetti. I risultati vengono assegnati a un `Boolean` valore che indica se i due oggetti sono identici.  
  
 [!code-vb[VbVbalrOperators#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#27)]  
  
 Come illustrato nell'esempio precedente, è possibile usare il `Is` operatore per eseguire il test sia ad associazione anticipata e gli oggetti ad associazione tardiva.  
  
## <a name="see-also"></a>Vedere anche

- [Operatore TypeOf](../../../visual-basic/language-reference/operators/typeof-operator.md)
- [Operatore IsNot](../../../visual-basic/language-reference/operators/isnot-operator.md)
- [Operatori di confronto in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Operatori ed espressioni](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
