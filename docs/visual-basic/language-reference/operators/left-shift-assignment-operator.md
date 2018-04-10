---
title: '&lt;&lt;= Operatore (Visual Basic)'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.<<=
helpviewer_keywords:
- operator <<=
- assignment statements [Visual Basic], compound
- <<= operator [Visual Basic]
- statements [Visual Basic], compound assignment
- operator<<=
- compound assignment statements [Visual Basic]
ms.assetid: 8ad26613-faff-4e2f-89ee-63feee33bfda
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5c5c36e4f91155c09d01b448777483941d018d9a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltlt-operator-visual-basic"></a>&lt;&lt;= Operatore (Visual Basic)
Esegue uno scorrimento aritmetico a sinistra sul valore di una variabile o proprietà e assegna il risultato alla variabile o alla proprietà.  
  
## <a name="syntax"></a>Sintassi  
  
```  
variableorproperty <<= amount  
```  
  
## <a name="parts"></a>Parti  
 `variableorproperty`  
 Obbligatorio. Variabile o proprietà di un tipo integrale (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, o `ULong`).  
  
 `amount`  
 Obbligatorio. Espressione numerica di un tipo di dati che si amplia in `Integer`.  
  
## <a name="remarks"></a>Note  
 L'elemento sul lato sinistro del `<<=` operatore può essere una semplice variabile scalare, una proprietà o un elemento della matrice. La variabile o proprietà non può essere [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
 Il `<<=` operatore prima esegue uno scorrimento aritmetico a sinistra sul valore della variabile o proprietà. L'operatore assegna il risultato dell'operazione alla variabile o alla proprietà.  
  
 Aritmetici non sono circolare, ovvero i bit spostati oltre un'estremità del risultato non sono reintrodotto a altra estremità. In uno spostamento a sinistra aritmetico, vengono eliminati i bit spostati oltre l'intervallo del tipo di dati di risultati, e le posizioni dei bit liberate a destra vengono impostate su zero.  
  
## <a name="overloading"></a>Overload  
 Il [<< operatore](../../../visual-basic/language-reference/operators/left-shift-operator.md) può essere *overload*, il che significa che una classe o struttura ridefinire il comportamento quando un operando ha il tipo di quella classe o struttura. L'overload di `<<` operatore influisce sul comportamento del `<<=` operatore. Se il codice utilizza `<<=` in una classe o struttura che esegue l'overload `<<`, assicurarsi di comprendere il comportamento ridefinito. Per ulteriori informazioni, vedere [routine di operatore](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il `<<=` operatore per spostare lo schema di bit di un `Integer` variabile da sinistra la quantità specificata e assegnare il risultato alla variabile.  
  
 [!code-vb[VbVbalrOperators#13](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/left-shift-assignment-operator_1.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Operatore <<](../../../visual-basic/language-reference/operators/left-shift-operator.md)  
 [Operatori di assegnazione](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [Operatori di spostamento bit](../../../visual-basic/language-reference/operators/bit-shift-operators.md)  
 [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Istruzioni](../../../visual-basic/programming-guide/language-features/statements.md)
