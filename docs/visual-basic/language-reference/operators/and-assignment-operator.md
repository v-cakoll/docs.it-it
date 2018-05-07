---
title: '&amp;= Operatore (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.&=
helpviewer_keywords:
- operator &=
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- '&= operator [Visual Basic]'
- compound assignment statements [Visual Basic]
ms.assetid: 0cf262fc-1a05-419a-a503-60013f111c8a
ms.openlocfilehash: c3db2d4095600f32af92d1a4ce1f806a3f032af0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="amp-operator-visual-basic"></a>&amp;= Operatore (Visual Basic)
Concatena una `String` espressione da un `String` variabile o proprietà e assegna il risultato alla variabile o proprietà.  
  
## <a name="syntax"></a>Sintassi  
  
```  
variableorproperty &= expression  
```  
  
## <a name="parts"></a>Parti  
 `variableorproperty`  
 Obbligatorio. Qualsiasi `String` variabile o proprietà.  
  
 `expression`  
 Obbligatorio. Qualsiasi espressione `String`.  
  
## <a name="remarks"></a>Note  
 L'elemento sul lato sinistro del `&=` operatore può essere una semplice variabile scalare, una proprietà o un elemento della matrice. La variabile o proprietà non può essere [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md). Il `&=` operatore concatena il `String` espressione alla sua destra per il `String` variabile o proprietà alla sua sinistra e assegna il risultato alla variabile o proprietà alla sua sinistra.  
  
## <a name="overloading"></a>Overload  
 Il [& operatore](../../../visual-basic/language-reference/operators/concatenation-operator.md) può essere *overload*, il che significa che una classe o struttura ridefinire il comportamento quando un operando ha il tipo di quella classe o struttura. L'overload di `&` operatore influisce sul comportamento del `&=` operatore. Se il codice utilizza `&=` in una classe o struttura che esegue l'overload `&`, assicurarsi di comprendere il comportamento ridefinito. Per ulteriori informazioni, vedere [routine di operatore](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il `&=` per concatenare due `String` variabili e assegnare il risultato alla prima variabile.  
  
 [!code-vb[VbVbalrOperators#3](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/and-assignment-operator_1.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Operatore &](../../../visual-basic/language-reference/operators/concatenation-operator.md)  
 [Operatore +=](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)  
 [Operatori di assegnazione](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [Operatori di concatenazione](../../../visual-basic/language-reference/operators/concatenation-operators.md)  
 [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Istruzioni](../../../visual-basic/programming-guide/language-features/statements.md)
