---
title: Operatore -=
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
ms.openlocfilehash: 44cb226d64e9f0b86c6566eb25fbafd6323a6d4c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347804"
---
# <a name="--operator-visual-basic"></a>Operatore -= (Visual Basic)
Sottrae il valore di un'espressione dal valore di una variabile o di una proprietà e assegna il risultato alla variabile o alla proprietà.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
variableorproperty -= expression  
```  
  
## <a name="parts"></a>Parti  
 `variableorproperty`  
 Obbligatoria. Qualsiasi variabile o proprietà numerica.  
  
 `expression`  
 Obbligatoria. Qualsiasi espressione numerica.  
  
## <a name="remarks"></a>Note  
 L'elemento sul lato sinistro dell'operatore `-=` può essere una variabile scalare semplice, una proprietà o un elemento di una matrice. La variabile o la proprietà non può essere di sola [lettura](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
 L'operatore `-=` prima di tutto sottrae il valore dell'espressione (sul lato destro dell'operatore) dal valore della variabile o della proprietà (sul lato sinistro dell'operatore). L'operatore assegna quindi il risultato dell'operazione alla variabile o alla proprietà.  
  
## <a name="overloading"></a>Overload  
 L' [operatore-(Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-operator.md) può essere sottoposto a *Overload*, il che significa che una classe o una struttura può ridefinire il comportamento quando un operando ha il tipo della classe o della struttura. L'overload dell'operatore `-` influiscono sul comportamento dell'operatore `-=`. Se il codice USA `-=` su una classe o una struttura che esegue l'overload di `-`, assicurarsi di comprendere il comportamento ridefinito. Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usato l'operatore `-=` per sottrarre una variabile `Integer` da un'altra e assegnare il risultato alla seconda variabile.  
  
 [!code-vb[VbVbalrOperators#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#11)]  
  
## <a name="see-also"></a>Vedere anche

- [Operatore-(Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-operator.md)
- [Operatori di assegnazione](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [Operatori aritmetici](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Istruzioni](../../../visual-basic/programming-guide/language-features/statements.md)
