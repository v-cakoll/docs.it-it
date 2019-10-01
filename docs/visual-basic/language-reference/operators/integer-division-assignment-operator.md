---
title: '\=Operatore (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- '\='
- vb.\=
helpviewer_keywords:
- '\= operator [Visual Basic]'
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- operator \= [Visual Basic]
- compound assignment statements [Visual Basic]
ms.assetid: 6f39915d-e398-4045-afcc-da6885e57b9c
ms.openlocfilehash: d7b4a6946cc38984272a6b63e14e8c1db2825a5e
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700671"
---
# <a name="-operator"></a>Operatore \\ =
Divide il valore di una variabile o di una proprietà in base al valore di un'espressione e assegna il risultato Integer alla variabile o alla proprietà.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
variableorproperty \= expression  
```  
  
## <a name="parts"></a>Parti  
 `variableorproperty`  
 Obbligatorio. Qualsiasi variabile o proprietà numerica.  
  
 `expression`  
 Obbligatorio. Qualsiasi espressione numerica.  
  
## <a name="remarks"></a>Note  
 L'elemento sul lato sinistro dell'operatore `\=` può essere una variabile scalare semplice, una proprietà o un elemento di una matrice. La variabile o la proprietà non può essere di sola [lettura](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
 L'operatore `\=` divide il valore di una variabile o di una proprietà a sinistra del valore a destra e assegna il risultato Integer alla variabile o alla proprietà a sinistra  
  
 Per ulteriori informazioni sulla divisione di interi, vedere [\ operator (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md).  
  
## <a name="overloading"></a>Overload  
 L'operatore `\` può essere sottoposto a *Overload*, il che significa che una classe o una struttura può ridefinire il comportamento quando un operando ha il tipo della classe o della struttura. L'overload dell'operatore `\` influiscono sul comportamento dell'operatore `\=`. Se il codice USA `\=` su una classe o una struttura che esegue l'overload `\`, assicurarsi di comprendere il comportamento ridefinito. Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usato l'operatore `\=` per dividere una variabile `Integer` per secondo e assegnare il risultato Integer alla prima variabile.  
  
 [!code-vb[VbVbalrOperators#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#19)]  
  
## <a name="see-also"></a>Vedere anche

- [Operatore \ (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md)
- [Operatore/= (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)
- [Operatori di assegnazione](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [Operatori aritmetici](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Istruzioni](../../../visual-basic/programming-guide/language-features/statements.md)
