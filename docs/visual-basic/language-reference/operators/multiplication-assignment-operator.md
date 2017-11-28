---
title: Operatore *= (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.*=
helpviewer_keywords:
- operator *=
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- '*= operator [Visual Basic]'
- compound assignment statements [Visual Basic]
ms.assetid: 96c86509-6eb8-4682-8226-3852e049376f
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2d0a2c638f3faaf20fadb745ef437941ee29d4f6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-visual-basic"></a>Operatore *= (Visual Basic)
Moltiplica il valore di una variabile o proprietà per il valore di un'espressione e assegna il risultato alla variabile o proprietà.  
  
## <a name="syntax"></a>Sintassi  
  
```  
variableorproperty *= expression  
```  
  
## <a name="parts"></a>Parti  
 `variableorproperty`  
 Obbligatorio. Qualsiasi variabile o proprietà numerica.  
  
 `expression`  
 Obbligatorio. Qualsiasi espressione numerica.  
  
## <a name="remarks"></a>Note  
 L'elemento sul lato sinistro del `*=` operatore può essere una semplice variabile scalare, una proprietà o un elemento della matrice. La variabile o proprietà non può essere [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
 Il `*=` operatore prima Moltiplica il valore dell'espressione (sul lato destro dell'operatore di) per il valore della variabile o proprietà (sul lato sinistro dell'operatore). L'operatore assegna il risultato dell'operazione per la variabile o proprietà.  
  
## <a name="overloading"></a>Overload  
 Il [* operatore](../../../visual-basic/language-reference/operators/multiplication-operator.md) può essere *overload*, il che significa che una classe o struttura ridefinire il comportamento quando un operando ha il tipo di quella classe o struttura. L'overload di `*` operatore influisce sul comportamento del `*=` operatore. Se il codice utilizza `*=` in una classe o struttura che esegue l'overload `*`, assicurarsi di comprendere il comportamento ridefinito. Per ulteriori informazioni, vedere [routine di operatore](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il `*=` operatore per moltiplicare una `Integer` variabile da un secondo e assegnare il risultato alla prima variabile.  
  
 [!code-vb[VbVbalrOperators#5](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/multiplication-assignment-operator_1.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Operatore *](../../../visual-basic/language-reference/operators/multiplication-operator.md)  
 [Operatori di assegnazione](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [Operatori aritmetici](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Istruzioni](../../../visual-basic/programming-guide/language-features/statements.md)
