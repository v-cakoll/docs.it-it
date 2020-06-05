---
title: '&amp;= (Operatore)'
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
ms.openlocfilehash: db42f7be7225b866eacf5b73066754e91cd1a0f7
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84371986"
---
# <a name="amp-operator-visual-basic"></a>&amp;Operatore = (Visual Basic)
Concatena un' `String` espressione a una `String` variabile o a una proprietà e assegna il risultato alla variabile o alla proprietà.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
variableorproperty &= expression  
```  
  
## <a name="parts"></a>Parti  
 `variableorproperty`  
 Obbligatorio. Qualsiasi `String` variabile o proprietà.  
  
 `expression`  
 Obbligatorio. Qualsiasi espressione `String` .  
  
## <a name="remarks"></a>Commenti  
 L'elemento sul lato sinistro dell' `&=` operatore può essere una variabile scalare semplice, una proprietà o un elemento di una matrice. La variabile o la proprietà non può essere di sola [lettura](../modifiers/readonly.md). L' `&=` operatore concatena l' `String` espressione a destra della `String` variabile o della proprietà a sinistra e assegna il risultato alla variabile o alla proprietà a sinistra.  
  
## <a name="overloading"></a>Overload  
 L' [operatore&](concatenation-operator.md) può essere sottoposto a *Overload*, il che significa che una classe o una struttura può ridefinire il comportamento quando un operando ha il tipo della classe o della struttura. L'overload dell' `&` operatore influiscono sul comportamento dell' `&=` operatore. Se il codice usa `&=` su una classe o una struttura che esegue l'overload di `&` , assicurarsi di comprendere il comportamento ridefinito. Per altre informazioni, vedere [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usato l' `&=` operatore per concatenare due `String` variabili e assegnare il risultato alla prima variabile.  
  
 [!code-vb[VbVbalrOperators#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#3)]  
  
## <a name="see-also"></a>Vedere anche

- [Operatore&](concatenation-operator.md)
- [Operatore + =](addition-assignment-operator.md)
- [Operatori di assegnazione](assignment-operators.md)
- [Operatori di concatenazione](concatenation-operators.md)
- [Precedenza tra gli operatori in Visual Basic](operator-precedence.md)
- [Elenco degli operatori per funzionalità](operators-listed-by-functionality.md)
- [Istruzioni](../../programming-guide/language-features/statements.md)
