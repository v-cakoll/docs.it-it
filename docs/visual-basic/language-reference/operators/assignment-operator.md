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
ms.openlocfilehash: 75f303219b9bf32613989f65f90a9096ef70e02e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350195"
---
# <a name="-operator-visual-basic"></a>Operatore = (Visual Basic)
Assigns a value to a variable or property.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
variableorproperty = value  
```  
  
## <a name="parts"></a>Parti  
 `variableorproperty`  
 Any writable variable or any property.  
  
 `value`  
 Any literal, constant, or expression.  
  
## <a name="remarks"></a>Note  
 The element on the left side of the equal sign (`=`) can be a simple scalar variable, a property, or an element of an array. The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md). The `=` operator assigns the value on its right to the variable or property on its left.  
  
> [!NOTE]
> The `=` operator is also used as a comparison operator. For details, see [Comparison Operators](../../../visual-basic/language-reference/operators/comparison-operators.md).  
  
## <a name="overloading"></a>Overload  
 The `=` operator can be overloaded only as a relational comparison operator, not as an assignment operator. Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 The following example demonstrates the assignment operator. The value on the right is assigned to the variable on the left.  
  
 [!code-vb[VbVbalrOperators#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#9)]  
  
## <a name="see-also"></a>Vedere anche

- [Operatore &=](../../../visual-basic/language-reference/operators/and-assignment-operator.md)
- [Operatore *=](../../../visual-basic/language-reference/operators/multiplication-assignment-operator.md)
- [Operatore +=](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)
- [-= Operator (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md)
- [/= Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)
- [\\= Operator](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)
- [Operatore ^=](../../../visual-basic/language-reference/operators/exponentiation-assignment-operator.md)
- [Istruzioni](../../../visual-basic/programming-guide/language-features/statements.md)
- [Operatori di confronto](../../../visual-basic/language-reference/operators/comparison-operators.md)
- [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)
- [Inferenza del tipo di variabile locale](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
