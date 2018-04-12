---
title: Operatore IsFalse (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.isfalse
helpviewer_keywords:
- AndAlso operator [Visual Basic]
- IsFalse operator [Visual Basic]
ms.assetid: 37fc9dbf-e5cc-4570-b93f-7213447974df
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d85fc51a75f82c65cf226b8239a8eee6585bd18a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="isfalse-operator-visual-basic"></a>Operatore IsFalse (Visual Basic)
Determina se un'espressione è `False`.  
  
 Non è possibile chiamare `IsFalse` in modo esplicito nel codice, ma Visual Basic compilatore può utilizzarlo per generare codice da `AndAlso` clausole. Se si definisce una classe o struttura e quindi utilizzare una variabile di quel tipo in un `AndAlso` clausola, è necessario definire `IsFalse` in quella classe o struttura.  
  
 Il compilatore considera il `IsFalse` e `IsTrue` operatori come un *coppia associata*. Ciò significa che se si definisce uno di essi, è inoltre necessario definire un'altra.  
  
> [!NOTE]
>  Il `IsFalse` operatore può essere *overload*, il che significa che una classe o struttura ridefinire il comportamento quando l'operando ha il tipo di quella classe o struttura. Se il codice Usa l'operatore in una classe o una struttura, assicurarsi di comprendere il comportamento ridefinito. Per ulteriori informazioni, vedere [routine di operatore](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 Esempio di codice seguente definisce la struttura di una struttura che include le definizioni per il `IsFalse` e `IsTrue` operatori.  
  
 [!code-vb[VbVbalrOperators#28](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/isfalse-operator_1.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Operatore IsTrue](../../../visual-basic/language-reference/operators/istrue-operator.md)  
 [Procedura: Definire un operatore](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [Operatore AndAlso](../../../visual-basic/language-reference/operators/andalso-operator.md)
