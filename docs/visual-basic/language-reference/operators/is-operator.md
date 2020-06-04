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
ms.openlocfilehash: 3cc0ae5f04358fbe6b2aabc50498f39ca7225164
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84370804"
---
# <a name="is-operator-visual-basic"></a>Operatore Is (Visual Basic)
Confronta due variabili di riferimento a oggetti.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
result = object1 Is object2  
```  
  
## <a name="parts"></a>Parti  
 `result`  
 Obbligatorio. Qualsiasi `Boolean` valore.  
  
 `object1`  
 Obbligatorio. Qualsiasi `Object` nome.  
  
 `object2`  
 Obbligatorio. Qualsiasi `Object` nome.  
  
## <a name="remarks"></a>Commenti  
 L' `Is` operatore determina se due riferimenti a oggetti si riferiscono allo stesso oggetto. Tuttavia, non esegue confronti di valori. Se `object1` ed `object2` entrambi fanno riferimento alla stessa istanza dell'oggetto, `result` è `True` ; in caso contrario, `result` è `False` .  
  
 `Is`può essere usato anche con la `TypeOf` parola chiave per creare un' `TypeOf` espressione... `Is` che verifica se una variabile oggetto è compatibile con un tipo di dati.  
  
> [!NOTE]
> La `Is` parola chiave viene inoltre utilizzata nell'oggetto [Select... Istruzione case](../statements/select-case-statement.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usato l' `Is` operatore per confrontare coppie di riferimenti a oggetti. I risultati vengono assegnati a un `Boolean` valore che indica se i due oggetti sono identici.  
  
 [!code-vb[VbVbalrOperators#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#27)]  
  
 Come illustrato nell'esempio precedente, è possibile usare l' `Is` operatore per testare gli oggetti ad associazione anticipata e ad associazione tardiva.  
  
## <a name="see-also"></a>Vedere anche

- [Operatore TypeOf](typeof-operator.md)
- [Operatore IsNot](isnot-operator.md)
- [Comparison Operators in Visual Basic](../../programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [Precedenza tra gli operatori in Visual Basic](operator-precedence.md)
- [Elenco degli operatori per funzionalità](operators-listed-by-functionality.md)
- [Operatori ed espressioni](../../programming-guide/language-features/operators-and-expressions/index.md)
