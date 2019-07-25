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
ms.openlocfilehash: abfe1489cb7e0d06b03c308e0704ce6f69ee55da
ms.sourcegitcommit: 1e7ac70be1b4d89708c0d9552897515f2cbf52c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2019
ms.locfileid: "68433811"
---
# <a name="byval-visual-basic"></a>ByVal (Visual Basic)
Specifica che un argomento viene passato [per valore](../../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md), in modo che la routine o proprietà chiamata non possa modificare il valore di una variabile sottostante l'argomento nel codice chiamante. Se non si specifica alcun modificatore, ByVal è il valore predefinito.
  
## <a name="remarks"></a>Note  
 Il modificatore `ByVal` può essere usato nei contesti seguenti:  
  
 [Istruzione Declare](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [Istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Istruzione Operator](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [Istruzione Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Istruzione Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato l'utilizzo del `ByVal` meccanismo di passaggio del parametro con un argomento di tipo riferimento. Nell'esempio, l'argomento è `c1`, un'istanza della classe. `Class1` `ByVal`impedisce al codice nelle procedure di modificare il valore sottostante dell'argomento di riferimento, `c1`, ma non protegge i campi e le proprietà accessibili di. `c1`  
  
 [!code-vb[VbVbalrKeywords#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class5.vb#10)]  
  
## <a name="see-also"></a>Vedere anche

- [Parole chiave](../../../visual-basic/language-reference/keywords/index.md)
- [Passaggio di argomenti per valore e per riferimento](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
