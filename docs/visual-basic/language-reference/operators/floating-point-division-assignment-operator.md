---
title: Operatore /= (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb./=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- /= operator [Visual Basic]
- operator /=
- compound assignment statements [Visual Basic]
ms.assetid: a1e22d0e-8380-4761-9da1-84fb51c34821
ms.openlocfilehash: d9d3fa021654d3be1b9d304beb83caa737660264
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58813990"
---
# <a name="-operator-visual-basic"></a>Operatore /= (Visual Basic)
Divide il valore di una variabile o proprietà per il valore di un'espressione e assegna il risultato a virgola mobile e la variabile o proprietà.  
  
## <a name="syntax"></a>Sintassi  
  
```  
variableorproperty /= expression  
```  
  
## <a name="parts"></a>Parti  
 `variableorproperty`  
 Obbligatorio. Qualsiasi variabile numerica o una proprietà.  
  
 `expression`  
 Obbligatorio. Qualsiasi espressione numerica.  
  
## <a name="remarks"></a>Note  
 L'elemento sul lato sinistro del `/=` operatore può essere una variabile semplice scalare, una proprietà o un elemento della matrice. La variabile o proprietà non può essere [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
 Il `/=` operatore divide innanzitutto il valore della variabile o proprietà (sul lato sinistro dell'operatore) per il valore dell'espressione (sul lato destro dell'operatore). L'operatore assegna quindi il risultato dell'operazione a virgola mobile e per la variabile o proprietà.  
  
 Questa istruzione assegna un `Double` valore alla variabile o proprietà a sinistra. Se `Option Strict` viene `On`, `variableorproperty` deve essere un `Double`. Se `Option Strict` viene `Off`, Visual Basic esegue una conversione implicita e assegna il valore risultante a `variableorproperty`, con un messaggio di errore in fase di esecuzione. Per altre informazioni, vedere [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) e [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).  
  
## <a name="overloading"></a>Overload  
 Il [/ operatore (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) può essere *sottoposto a overload*, il che significa che una classe o struttura può ridefinire il comportamento quando un operando ha il tipo di quella classe o struttura. L'overload di `/` operatore influisce sul comportamento del `/=` operatore. Se il codice usi `/=` in una classe o struttura che esegue l'overload `/`, assicurarsi di comprendere il comportamento ridefinito. Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il `/=` operatore per dividere un `Integer` variabile da un secondo e di assegnare il quoziente per la prima variabile.  
  
 [!code-vb[VbVbalrOperators#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#17)]  
  
## <a name="see-also"></a>Vedere anche

- [/ Operatore (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)
- [\\= Operatore](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)
- [Operatori di assegnazione](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [Operatori aritmetici](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Istruzioni](../../../visual-basic/programming-guide/language-features/statements.md)
