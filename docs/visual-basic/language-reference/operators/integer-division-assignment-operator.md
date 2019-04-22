---
title: '\= Operatore (Visual Basic)'
ms.date: 07/20/2015
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
ms.openlocfilehash: 377a14a76f67e938f24c973b5946abd63f851bfd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58842538"
---
# <a name="-operator"></a>\\= Operatore
Divide il valore di una variabile o proprietà per il valore di un'espressione e assegna il risultato di integer alla variabile o proprietà.  
  
## <a name="syntax"></a>Sintassi  
  
```  
variableorproperty \= expression  
```  
  
## <a name="parts"></a>Parti  
 `variableorproperty`  
 Obbligatorio. Qualsiasi variabile numerica o una proprietà.  
  
 `expression`  
 Obbligatorio. Qualsiasi espressione numerica.  
  
## <a name="remarks"></a>Note  
 L'elemento sul lato sinistro del `\=` operatore può essere una variabile semplice scalare, una proprietà o un elemento della matrice. La variabile o proprietà non può essere [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
 Il `\=` operatore divide il valore di una variabile o proprietà alla sua sinistra per il valore alla sua destra e assegna il risultato di integer per la variabile o una proprietà alla sua sinistra  
  
 Per altre informazioni sulla divisione di interi, vedere [\ (operatore) (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md).  
  
## <a name="overloading"></a>Overload  
 Il `\` operatore può essere *sottoposto a overload*, il che significa che una classe o struttura può ridefinire il comportamento quando un operando ha il tipo di quella classe o struttura. L'overload di `\` operatore influisce sul comportamento del `\=` operatore. Se il codice usi `\=` in una classe o struttura che esegue l'overload `\`, assicurarsi di comprendere il comportamento ridefinito. Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il `\=` operatore per dividere un `Integer` variabile da un secondo e di assegnare l'intero risultato per la prima variabile.  
  
 [!code-vb[VbVbalrOperators#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#19)]  
  
## <a name="see-also"></a>Vedere anche

- [\ Operatore (Visual Basic)](../../../visual-basic/language-reference/operators/integer-division-operator.md)
- [/ = (Operatore) (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)
- [Operatori di assegnazione](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [Operatori aritmetici](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Istruzioni](../../../visual-basic/programming-guide/language-features/statements.md)
