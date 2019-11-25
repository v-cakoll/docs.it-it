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
Compares two object reference variables.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
result = object1 Is object2  
```  
  
## <a name="parts"></a>Parti  
 `result`  
 Obbligatorio. Any `Boolean` value.  
  
 `object1`  
 Obbligatorio. Any `Object` name.  
  
 `object2`  
 Obbligatorio. Any `Object` name.  
  
## <a name="remarks"></a>Note  
 The `Is` operator determines if two object references refer to the same object. However, it does not perform value comparisons. If `object1` and `object2` both refer to the exact same object instance, `result` is `True`; if they do not, `result` is `False`.  
  
 `Is` can also be used with the `TypeOf` keyword to make a `TypeOf`...`Is` expression, which tests whether an object variable is compatible with a data type.  
  
> [!NOTE]
> The `Is` keyword is also used in the [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md).  
  
## <a name="example"></a>Esempio  
 The following example uses the `Is` operator to compare pairs of object references. The results are assigned to a `Boolean` value representing whether the two objects are identical.  
  
 [!code-vb[VbVbalrOperators#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#27)]  
  
 As the preceding example demonstrates, you can use the `Is` operator to test both early bound and late bound objects.  
  
## <a name="see-also"></a>Vedere anche

- [Operatore TypeOf](../../../visual-basic/language-reference/operators/typeof-operator.md)
- [Operatore IsNot](../../../visual-basic/language-reference/operators/isnot-operator.md)
- [Comparison Operators in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Operatori ed espressioni](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
