---
title: Operatore *=
ms.date: 07/20/2015
f1_keywords:
- vb.*=
helpviewer_keywords:
- operator *=
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- '*= operator [Visual Basic]'
- compound assignment statements [Visual Basic]
ms.assetid: 96c86509-6eb8-4682-8226-3852e049376f
ms.openlocfilehash: 4b60fa44a92bff683e13f850da025d7fe753618d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349779"
---
# <a name="-operator-visual-basic"></a>Operatore *= (Visual Basic)
Moltiplica il valore di una variabile o di una proprietà in base al valore di un'espressione e assegna il risultato alla variabile o alla proprietà.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
variableorproperty *= expression  
```  
  
## <a name="parts"></a>Parti  
 `variableorproperty`  
 Obbligatoria. Qualsiasi variabile o proprietà numerica.  
  
 `expression`  
 Obbligatoria. Qualsiasi espressione numerica.  
  
## <a name="remarks"></a>Osservazioni  
 L'elemento sul lato sinistro dell'operatore `*=` può essere una variabile scalare semplice, una proprietà o un elemento di una matrice. La variabile o la proprietà non può essere di sola [lettura](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
 L'operatore `*=` moltiplica innanzitutto il valore dell'espressione (sul lato destro dell'operatore) in base al valore della variabile o della proprietà (sul lato sinistro dell'operatore). L'operatore assegna quindi il risultato dell'operazione alla variabile o alla proprietà.  
  
## <a name="overloading"></a>Overload  
 L' [operatore *](../../../visual-basic/language-reference/operators/multiplication-operator.md) può essere sottoposto a *Overload*, il che significa che una classe o una struttura può ridefinire il comportamento quando un operando ha il tipo della classe o della struttura. L'overload dell'operatore `*` influiscono sul comportamento dell'operatore `*=`. Se il codice USA `*=` su una classe o una struttura che esegue l'overload di `*`, assicurarsi di comprendere il comportamento ridefinito. Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usato l'operatore `*=` per moltiplicare una `Integer` variabile di secondo e assegnare il risultato alla prima variabile.  
  
 [!code-vb[VbVbalrOperators#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#5)]  
  
## <a name="see-also"></a>Vedere anche

- [Operatore *](../../../visual-basic/language-reference/operators/multiplication-operator.md)
- [Operatori di assegnazione](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [Operatori aritmetici](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Istruzioni](../../../visual-basic/programming-guide/language-features/statements.md)
