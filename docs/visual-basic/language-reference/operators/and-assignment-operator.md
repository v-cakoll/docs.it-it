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
ms.openlocfilehash: a79e779d8fcf549daeabc494e0a55deee30b5d22
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58835466"
---
# <a name="amp-operator-visual-basic"></a>&amp;= Operatore (Visual Basic)
Concatena una `String` espressione da un `String` proprietà o variabile e assegna il risultato alla variabile o proprietà.  
  
## <a name="syntax"></a>Sintassi  
  
```  
variableorproperty &= expression  
```  
  
## <a name="parts"></a>Parti  
 `variableorproperty`  
 Obbligatorio. Qualsiasi `String` variabile o una proprietà.  
  
 `expression`  
 Obbligatorio. Qualsiasi espressione `String` .  
  
## <a name="remarks"></a>Note  
 L'elemento sul lato sinistro del `&=` operatore può essere una variabile semplice scalare, una proprietà o un elemento della matrice. La variabile o proprietà non può essere [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md). Il `&=` operatore consente di concatenare il `String` espressione alla sua destra per il `String` variabile o una proprietà alla sua sinistra e assegna il risultato alla variabile o proprietà alla sua sinistra.  
  
## <a name="overloading"></a>Overload  
 Il [& Operator](../../../visual-basic/language-reference/operators/concatenation-operator.md) può essere *sottoposto a overload*, il che significa che una classe o struttura può ridefinire il comportamento quando un operando ha il tipo di quella classe o struttura. L'overload di `&` operatore influisce sul comportamento del `&=` operatore. Se il codice usi `&=` in una classe o struttura che esegue l'overload `&`, assicurarsi di comprendere il comportamento ridefinito. Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il `&=` per concatenare due `String` variabili e assegna il risultato per la prima variabile.  
  
 [!code-vb[VbVbalrOperators#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#3)]  
  
## <a name="see-also"></a>Vedere anche

- [Operatore &](../../../visual-basic/language-reference/operators/concatenation-operator.md)
- [Operatore +=](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)
- [Operatori di assegnazione](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [Operatori di concatenazione](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Istruzioni](../../../visual-basic/programming-guide/language-features/statements.md)
