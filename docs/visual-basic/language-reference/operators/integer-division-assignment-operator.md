---
title: Operatore \=
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
ms.openlocfilehash: a546d8b0c9b3852386970f80d3da96794da2351c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84370947"
---
# <a name="-operator"></a>\\= (Operatore)
Divide il valore di una variabile o di una proprietà in base al valore di un'espressione e assegna il risultato Integer alla variabile o alla proprietà.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
variableorproperty \= expression  
```  
  
## <a name="parts"></a>Parti  
 `variableorproperty`  
 Obbligatorio. Qualsiasi variabile o proprietà numerica.  
  
 `expression`  
 Obbligatorio. Qualsiasi espressione numerica.  
  
## <a name="remarks"></a>Commenti  
 L'elemento sul lato sinistro dell' `\=` operatore può essere una variabile scalare semplice, una proprietà o un elemento di una matrice. La variabile o la proprietà non può essere di sola [lettura](../modifiers/readonly.md).  
  
 L' `\=` operatore divide il valore di una variabile o di una proprietà a sinistra del valore a destra e assegna il risultato Integer alla variabile o alla proprietà a sinistra  
  
 Per ulteriori informazioni sulla divisione di interi, vedere [\ operator (Visual Basic)](integer-division-operator.md).  
  
## <a name="overloading"></a>Overload  
 L' `\` operatore può essere sottoposto a *Overload*, il che significa che una classe o una struttura può ridefinire il comportamento quando un operando ha il tipo della classe o della struttura. L'overload dell' `\` operatore influiscono sul comportamento dell' `\=` operatore. Se il codice usa `\=` su una classe o una struttura che esegue l'overload di `\` , assicurarsi di comprendere il comportamento ridefinito. Per altre informazioni, vedere [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usato l' `\=` operatore per dividere una `Integer` variabile per secondo e assegnare il risultato Integer alla prima variabile.  
  
 [!code-vb[VbVbalrOperators#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#19)]  
  
## <a name="see-also"></a>Vedere anche

- [Operatore \ (Visual Basic)](integer-division-operator.md)
- [Operatore /= (Visual Basic)](floating-point-division-assignment-operator.md)
- [Operatori di assegnazione](assignment-operators.md)
- [Operatori aritmetici](arithmetic-operators.md)
- [Precedenza tra gli operatori in Visual Basic](operator-precedence.md)
- [Elenco degli operatori per funzionalità](operators-listed-by-functionality.md)
- [Istruzioni](../../programming-guide/language-features/statements.md)
