---
title: Operatore IsFalse (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.isfalse
helpviewer_keywords:
- AndAlso operator [Visual Basic]
- IsFalse operator [Visual Basic]
ms.assetid: 37fc9dbf-e5cc-4570-b93f-7213447974df
ms.openlocfilehash: 9f25c406038486224c2c4708c86ef86889c44c15
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62013543"
---
# <a name="isfalse-operator-visual-basic"></a>Operatore IsFalse (Visual Basic)
Determina se un'espressione è `False`.  
  
 Non è possibile chiamare `IsFalse` in modo esplicito nel codice, ma Visual Basic compilatore può utilizzarlo per generare codice da `AndAlso` clausole. Se si definisce una classe o struttura e quindi usare una variabile di quel tipo in un `AndAlso` clausola, è necessario definire `IsFalse` in quella classe o struttura.  
  
 Il compilatore considera il `IsFalse` e `IsTrue` operatori come una *coppia associata*. Ciò significa che se si definisce uno di essi, è necessario anche definire un'altra.  
  
> [!NOTE]
>  Il `IsFalse` operatore può essere *sottoposto a overload*, il che significa che una classe o struttura può ridefinire il comportamento quando l'operando ha il tipo di quella classe o struttura. Se il codice Usa l'operatore su una classe o struttura, assicurarsi di che comprendere il comportamento ridefinito. Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 Esempio di codice seguente definisce la struttura di una struttura che include le definizioni per il `IsFalse` e `IsTrue` operatori.  
  
 [!code-vb[VbVbalrOperators#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#28)]  
  
## <a name="see-also"></a>Vedere anche

- [Operatore IsTrue](../../../visual-basic/language-reference/operators/istrue-operator.md)
- [Procedura: Definire un operatore](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [Operatore AndAlso](../../../visual-basic/language-reference/operators/andalso-operator.md)
