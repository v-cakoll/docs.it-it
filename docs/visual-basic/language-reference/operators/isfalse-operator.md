---
title: Operatore IsFalse
ms.date: 07/20/2015
f1_keywords:
- vb.isfalse
helpviewer_keywords:
- AndAlso operator [Visual Basic]
- IsFalse operator [Visual Basic]
ms.assetid: 37fc9dbf-e5cc-4570-b93f-7213447974df
ms.openlocfilehash: 7c5ad5fa0b72370eeb19fbaced88807570467552
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84370674"
---
# <a name="isfalse-operator-visual-basic"></a>Operatore IsFalse (Visual Basic)
Determina se un'espressione è `False` .  
  
 Non è possibile chiamare `IsFalse` in modo esplicito nel codice, ma il compilatore Visual Basic può usarlo per generare codice da `AndAlso` clausole. Se si definisce una classe o una struttura e quindi si usa una variabile di quel tipo in una `AndAlso` clausola, è necessario definire `IsFalse` su tale classe o struttura.  
  
 Il compilatore considera gli `IsFalse` `IsTrue` operatori e come una *coppia corrispondente*. Ciò significa che se si definisce uno di essi, è necessario definire anche l'altro.  
  
> [!NOTE]
> L' `IsFalse` operatore può essere sottoposto a *Overload*, il che significa che una classe o una struttura può ridefinire il comportamento quando il relativo operando ha il tipo della classe o della struttura. Se il codice usa questo operatore su una classe o una struttura di questo tipo, assicurarsi di comprendere il comportamento ridefinito. Per altre informazioni, vedere [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice seguente viene definita la struttura di una struttura che include definizioni per gli `IsFalse` `IsTrue` operatori e.  
  
 [!code-vb[VbVbalrOperators#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#28)]  
  
## <a name="see-also"></a>Vedere anche

- [Operatore IsTrue](istrue-operator.md)
- [Procedura: definire un operatore](../../programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [Operatore AndAlso](andalso-operator.md)
