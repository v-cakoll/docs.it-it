---
title: Operatore -= (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.-=
helpviewer_keywords:
- -= operator [Visual Basic]
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- operator -=
- compound assignment statements [Visual Basic]
ms.assetid: 5ead0c37-ae50-48f7-8435-8e341d81cae1
ms.openlocfilehash: be1ff4f10f6b30d8448d2441ee3ad2c1e2f80e2d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62013491"
---
# <a name="--operator-visual-basic"></a>Operatore -= (Visual Basic)
Sottrae il valore di un'espressione rispetto a quello di una proprietà o variabile e assegna il risultato alla variabile o proprietà.  
  
## <a name="syntax"></a>Sintassi  
  
```  
variableorproperty -= expression  
```  
  
## <a name="parts"></a>Parti  
 `variableorproperty`  
 Obbligatorio. Qualsiasi variabile numerica o una proprietà.  
  
 `expression`  
 Obbligatorio. Qualsiasi espressione numerica.  
  
## <a name="remarks"></a>Note  
 L'elemento sul lato sinistro del `-=` operatore può essere una variabile semplice scalare, una proprietà o un elemento della matrice. La variabile o proprietà non può essere [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
 Il `-=` operatore sottrae prima il valore dell'espressione (sul lato destro dell'operatore) dal valore della variabile o proprietà (sul lato sinistro dell'operatore). L'operatore assegna il risultato dell'operazione per la variabile o proprietà.  
  
## <a name="overloading"></a>Overload  
 Il [-operatore (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-operator.md) può essere *sottoposto a overload*, il che significa che una classe o struttura può ridefinire il comportamento quando un operando ha il tipo di quella classe o struttura. L'overload di `-` operatore influisce sul comportamento del `-=` operatore. Se il codice usi `-=` in una classe o struttura che esegue l'overload `-`, assicurarsi di comprendere il comportamento ridefinito. Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il `-=` operatore per sottrarre uno `Integer` da un'altra variabile e assegna il risultato alla variabile di quest'ultimo.  
  
 [!code-vb[VbVbalrOperators#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#11)]  
  
## <a name="see-also"></a>Vedere anche

- [-Operatore (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-operator.md)
- [Operatori di assegnazione](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [Operatori aritmetici](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Istruzioni](../../../visual-basic/programming-guide/language-features/statements.md)
