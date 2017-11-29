---
title: '\=(Operatore)'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5ba74f7a433687b306e8b4273f3a2a6d60583396
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="-operator"></a>\\= (Operatore)
Divide il valore di una variabile o proprietà per il valore di un'espressione e assegna il risultato di tipo integer per la variabile o proprietà.  
  
## <a name="syntax"></a>Sintassi  
  
```  
variableorproperty \= expression  
```  
  
## <a name="parts"></a>Parti  
 `variableorproperty`  
 Obbligatorio. Qualsiasi variabile o proprietà numerica.  
  
 `expression`  
 Obbligatorio. Qualsiasi espressione numerica.  
  
## <a name="remarks"></a>Note  
 L'elemento sul lato sinistro del `\=` operatore può essere una semplice variabile scalare, una proprietà o un elemento della matrice. La variabile o proprietà non può essere [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
 Il `\=` operatore divide il valore di una variabile o proprietà alla sua sinistra per il valore alla sua destra e assegna il risultato di tipo integer per la variabile o proprietà alla sua sinistra  
  
 Per ulteriori informazioni sulla divisione di integer, vedere [\ (operatore) (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md).  
  
## <a name="overloading"></a>Overload  
 Il `\` operatore può essere *overload*, il che significa che una classe o struttura ridefinire il comportamento quando un operando ha il tipo di quella classe o struttura. L'overload di `\` operatore influisce sul comportamento del `\=` operatore. Se il codice utilizza `\=` in una classe o struttura che esegue l'overload `\`, assicurarsi di comprendere il comportamento ridefinito. Per ulteriori informazioni, vedere [routine di operatore](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il `\=` operatore per dividere una `Integer` variabile da un secondo e assegnare l'intero risultato per la prima variabile.  
  
 [!code-vb[VbVbalrOperators#19](codesnippet/VisualBasic/integer-division-assignment-operator_1.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [\ Operatore (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md)  
 [/ = (Operatore) (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)  
 [Operatori di assegnazione](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [Operatori aritmetici](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Istruzioni](../../../visual-basic/programming-guide/language-features/statements.md)
