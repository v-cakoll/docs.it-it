---
title: Operatore IsFalse (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.isfalse
helpviewer_keywords:
- AndAlso operator [Visual Basic]
- IsFalse operator [Visual Basic]
ms.assetid: 37fc9dbf-e5cc-4570-b93f-7213447974df
ms.openlocfilehash: e84b2162eb0763725f05bc52d5c4223d7c430b81
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33600047"
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
