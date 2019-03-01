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
ms.openlocfilehash: edee47e41ca78175a6fb24ed5eac255c03de0901
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56972573"
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
  
 [!code-vb[VbVbalrKeywords#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class5.vb#10)]  
  
## <a name="see-also"></a>Vedere anche
- [Parole chiave](../../../visual-basic/language-reference/keywords/index.md)
- [Passaggio di argomenti per valore e per riferimento](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
