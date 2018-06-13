---
title: Operatore = (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Assign
- vb.=
helpviewer_keywords:
- = operator [Visual Basic]
- = assignment statements [Visual Basic]
ms.assetid: 2dac2e49-86c8-42f8-80c1-458452fb5e29
ms.openlocfilehash: 55b3a8201940a6fec351327aaa88e4ac1ee9246a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603600"
---
# <a name="-operator-visual-basic"></a>Operatore = (Visual Basic)
Assegna un valore a una variabile o proprietà.  
  
## <a name="syntax"></a>Sintassi  
  
```  
variableorproperty = value  
```  
  
## <a name="parts"></a>Parti  
 `variableorproperty`  
 Qualsiasi variabile modificabile o qualsiasi proprietà.  
  
 `value`  
 Qualsiasi valore letterale costante o espressione.  
  
## <a name="remarks"></a>Note  
 L'elemento a sinistra del segno di uguale (`=`) può essere una semplice variabile scalare, una proprietà o un elemento della matrice. La variabile o proprietà non può essere [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md). Il `=` operatore assegna il valore alla sua destra alla variabile o proprietà alla sua sinistra.  
  
> [!NOTE]
>  Il `=` operatore viene inoltre utilizzato come operatore di confronto. Per informazioni dettagliate, vedere [gli operatori di confronto](../../../visual-basic/language-reference/operators/comparison-operators.md).  
  
## <a name="overloading"></a>Overload  
 Il `=` operatore può essere sottoposto a overload solo come operatore di confronto relazionale, non come un operatore di assegnazione. Per ulteriori informazioni, vedere [routine di operatore](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato l'operatore di assegnazione. Il valore a destra viene assegnato alla variabile a sinistra.  
  
 [!code-vb[VbVbalrOperators#9](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/assignment-operator_1.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Operatore &=](../../../visual-basic/language-reference/operators/and-assignment-operator.md)  
 [Operatore *=](../../../visual-basic/language-reference/operators/multiplication-assignment-operator.md)  
 [Operatore +=](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)  
 [-= Operatore (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md)  
 [/ = (Operatore) (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)  
 [\\= (Operatore)](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)  
 [Operatore ^=](../../../visual-basic/language-reference/operators/exponentiation-assignment-operator.md)  
 [Istruzioni](../../../visual-basic/programming-guide/language-features/statements.md)  
 [Operatori di confronto](../../../visual-basic/language-reference/operators/comparison-operators.md)  
 [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)  
 [Inferenza del tipo di variabile locale](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
