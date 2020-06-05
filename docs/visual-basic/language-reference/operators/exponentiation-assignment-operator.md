---
title: Operatore ^=
ms.date: 07/20/2015
f1_keywords:
- vb.^=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- ^= operator [Visual Basic]
- compound assignment statements [Visual Basic]
ms.assetid: 397da132-2d96-4a85-a7bc-f7c730a608c9
ms.openlocfilehash: e631cc9a484b56ee059449ca1fbd9fc69405333d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84371401"
---
# <a name="-operator-visual-basic"></a>Operatore ^= (Visual Basic)
Genera il valore di una variabile o di una proprietà alla potenza di un'espressione e assegna il risultato alla variabile o alla proprietà.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
variableorproperty ^= expression  
```  
  
## <a name="parts"></a>Parti  
 `variableorproperty`  
 Obbligatorio. Qualsiasi variabile o proprietà numerica.  
  
 `expression`  
 Obbligatorio. Qualsiasi espressione numerica.  
  
## <a name="remarks"></a>Commenti  
 L'elemento sul lato sinistro dell' `^=` operatore può essere una variabile scalare semplice, una proprietà o un elemento di una matrice. La variabile o la proprietà non può essere di sola [lettura](../modifiers/readonly.md).  
  
 L' `^=` operatore eleva prima di tutto il valore della variabile o della proprietà (sul lato sinistro dell'operatore) alla potenza del valore dell'espressione (sul lato destro dell'operatore). L'operatore assegna quindi il risultato dell'operazione alla variabile o alla proprietà.  
  
 Visual Basic esegue sempre l'elevamento a potenza nel [tipo di dati Double](../data-types/double-data-type.md). Gli operandi di qualsiasi tipo diverso vengono convertiti in `Double` e il risultato è sempre `Double` .  
  
 Il valore di `expression` può essere frazionario, negativo o entrambi.  
  
## <a name="overloading"></a>Overload  
 L' [operatore ^](exponentiation-operator.md) può essere sottoposto a *Overload*, il che significa che una classe o una struttura può ridefinire il comportamento quando un operando ha il tipo della classe o della struttura. L'overload dell' `^` operatore influiscono sul comportamento dell' `^=` operatore. Se il codice usa `^=` su una classe o una struttura che esegue l'overload di `^` , assicurarsi di comprendere il comportamento ridefinito. Per altre informazioni, vedere [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usato l' `^=` operatore per aumentare il valore di una `Integer` variabile alla potenza di una seconda variabile e assegnare il risultato alla prima variabile.  
  
 [!code-vb[VbVbalrOperators#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#21)]  
  
## <a name="see-also"></a>Vedere anche

- [Operatore ^](exponentiation-operator.md)
- [Operatori di assegnazione](assignment-operators.md)
- [Operatori aritmetici](arithmetic-operators.md)
- [Precedenza tra gli operatori in Visual Basic](operator-precedence.md)
- [Elenco degli operatori per funzionalità](operators-listed-by-functionality.md)
- [Istruzioni](../../programming-guide/language-features/statements.md)
