---
title: Operatore Is (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.is
helpviewer_keywords:
- comparison operators [Visual Basic]
- equivalent objects
- TypeOf...Is expression
- Is operator [Visual Basic]
ms.assetid: 8045a6c8-2a83-45b6-ad47-d09a704c656d
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4b1f3f0fa1fd782550c08c816f47b7541399198e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
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
  
 `Is`può anche essere utilizzato con il `TypeOf` (parola chiave) per rendere un `TypeOf`... `Is` espressione, che verifica se una variabile oggetto è compatibile con un tipo di dati.  
  
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
