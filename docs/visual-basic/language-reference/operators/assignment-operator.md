---
title: Operatore =
ms.date: 07/20/2015
f1_keywords:
- vb.Assign
- vb.=
helpviewer_keywords:
- = operator [Visual Basic]
- = assignment statements [Visual Basic]
ms.assetid: 2dac2e49-86c8-42f8-80c1-458452fb5e29
ms.openlocfilehash: 516cb21e02d9fb2cd4b8d72282bb74163e1fb14b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84371765"
---
# <a name="-operator-visual-basic"></a>Operatore = (Visual Basic)
Assegna un valore a una variabile o a una proprietà.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
variableorproperty = value  
```  
  
## <a name="parts"></a>Parti  
 `variableorproperty`  
 Qualsiasi variabile scrivibile o qualsiasi proprietà.  
  
 `value`  
 Qualsiasi valore letterale, costante o espressione.  
  
## <a name="remarks"></a>Commenti  
 L'elemento sul lato sinistro del segno di uguale ( `=` ) può essere una variabile scalare semplice, una proprietà o un elemento di una matrice. La variabile o la proprietà non può essere di sola [lettura](../modifiers/readonly.md). L' `=` operatore assegna il valore a destra alla variabile o alla proprietà a sinistra.  
  
> [!NOTE]
> L' `=` operatore viene utilizzato anche come operatore di confronto. Per informazioni dettagliate, vedere [operatori di confronto](comparison-operators.md).  
  
## <a name="overloading"></a>Overload  
 `=`È possibile eseguire l'overload dell'operatore solo come operatore di confronto relazionale, non come operatore di assegnazione. Per altre informazioni, vedere [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato l'operatore di assegnazione. Il valore a destra viene assegnato alla variabile a sinistra.  
  
 [!code-vb[VbVbalrOperators#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#9)]  
  
## <a name="see-also"></a>Vedere anche

- [Operatore&=](and-assignment-operator.md)
- [Operatore * =](multiplication-assignment-operator.md)
- [Operatore + =](addition-assignment-operator.md)
- [Operatore-= (Visual Basic)](subtraction-assignment-operator.md)
- [Operatore /= (Visual Basic)](floating-point-division-assignment-operator.md)
- [\\= (Operatore)](integer-division-assignment-operator.md)
- [^ = (Operatore)](exponentiation-assignment-operator.md)
- [Istruzioni](../../programming-guide/language-features/statements.md)
- [Operatori di confronto](comparison-operators.md)
- [ReadOnly](../modifiers/readonly.md)
- [Inferenza del tipo di variabile locale](../../programming-guide/language-features/variables/local-type-inference.md)
