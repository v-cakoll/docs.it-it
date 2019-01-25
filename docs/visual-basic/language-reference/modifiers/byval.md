---
title: ByVal (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ByVal
- ByVal
helpviewer_keywords:
- ByVal keyword [Visual Basic], contexts
- ByVal keyword [Visual Basic]
ms.assetid: 1eaf4e58-b305-4785-9e3d-e416b9c75598
ms.openlocfilehash: 6fa87db4fbab961dd1aa526e2ac8ff15b031005b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54650080"
---
# <a name="byval-visual-basic"></a>ByVal (Visual Basic)
Specifica che un argomento è passato in modo tale che la routine o proprietà chiamata non è possibile modificare il valore di una variabile sottostante all'argomento nel codice chiamante.  
  
## <a name="remarks"></a>Note  
 Il modificatore `ByVal` può essere usato nei contesti seguenti:  
  
 [Istruzione Declare](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [Istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Istruzione Operator](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [Istruzione Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Istruzione Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato l'utilizzo del `ByVal` meccanismo con un argomento di tipo di riferimento di passaggio dei parametri. Nell'esempio, è l'argomento `c1`, un'istanza della classe `Class1`. `ByVal` impedisce che la modifica del valore sottostante dell'argomento di riferimento, il codice nelle procedure riportate `c1`, ma non protegge accessibili campi e proprietà di `c1`.  
  
 [!code-vb[VbVbalrKeywords#10](../../../visual-basic/language-reference/codesnippet/VisualBasic/byval_1.vb)]  
  
## <a name="see-also"></a>Vedere anche
- [Parole chiave](../../../visual-basic/language-reference/keywords/index.md)
- [Passaggio di argomenti per valore e per riferimento](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
