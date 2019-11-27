---
title: Operatore IsFalse
ms.date: 07/20/2015
f1_keywords:
- vb.isfalse
helpviewer_keywords:
- AndAlso operator [Visual Basic]
- IsFalse operator [Visual Basic]
ms.assetid: 37fc9dbf-e5cc-4570-b93f-7213447974df
ms.openlocfilehash: 51b7bfb2cf5301a39818e6566b408ee0677689f2
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349521"
---
# <a name="isfalse-operator-visual-basic"></a>Operatore IsFalse (Visual Basic)
Determina se un'espressione viene `False`.  
  
 Non è possibile chiamare `IsFalse` in modo esplicito nel codice, ma il compilatore Visual Basic può usarlo per generare codice da `AndAlso` clausole. Se si definisce una classe o una struttura e quindi si usa una variabile di quel tipo in una clausola `AndAlso`, è necessario definire `IsFalse` sulla classe o sulla struttura.  
  
 Il compilatore considera gli operatori `IsFalse` e `IsTrue` come *coppia corrispondente*. Ciò significa che se si definisce uno di essi, è necessario definire anche l'altro.  
  
> [!NOTE]
> L'operatore `IsFalse` può essere sottoposto a *Overload*, il che significa che una classe o una struttura può ridefinire il comportamento quando il relativo operando ha il tipo della classe o della struttura. Se il codice usa questo operatore su una classe o una struttura di questo tipo, assicurarsi di comprendere il comportamento ridefinito. Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice seguente viene definita la struttura di una struttura che include definizioni per gli operatori `IsFalse` e `IsTrue`.  
  
 [!code-vb[VbVbalrOperators#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#28)]  
  
## <a name="see-also"></a>Vedere anche

- [Operatore IsTrue](../../../visual-basic/language-reference/operators/istrue-operator.md)
- [Procedura: Definire un operatore](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [Operatore AndAlso](../../../visual-basic/language-reference/operators/andalso-operator.md)
