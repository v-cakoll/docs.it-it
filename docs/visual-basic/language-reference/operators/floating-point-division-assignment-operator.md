---
title: Operatore /=
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
ms.openlocfilehash: 48ae78630aa66ad804d539f88524c456cf805889
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84371245"
---
# <a name="-operator-visual-basic"></a>Operatore /= (Visual Basic)
Divide il valore di una variabile o di una proprietà in base al valore di un'espressione e assegna il risultato a virgola mobile alla variabile o alla proprietà.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
variableorproperty /= expression  
```  
  
## <a name="parts"></a>Parti  
 `variableorproperty`  
 Obbligatorio. Qualsiasi variabile o proprietà numerica.  
  
 `expression`  
 Obbligatorio. Qualsiasi espressione numerica.  
  
## <a name="remarks"></a>Commenti  
 L'elemento sul lato sinistro dell' `/=` operatore può essere una variabile scalare semplice, una proprietà o un elemento di una matrice. La variabile o la proprietà non può essere di sola [lettura](../modifiers/readonly.md).  
  
 L' `/=` operatore divide prima di tutto il valore della variabile o della proprietà (sul lato sinistro dell'operatore) per il valore dell'espressione (sul lato destro dell'operatore). L'operatore assegna quindi il risultato a virgola mobile dell'operazione alla variabile o alla proprietà.  
  
 Questa istruzione assegna un `Double` valore alla variabile o alla proprietà a sinistra. Se `Option Strict` è `On` , `variableorproperty` deve essere un `Double` oggetto. Se `Option Strict` è `Off` , Visual Basic esegue una conversione implicita e assegna il valore risultante a `variableorproperty` , con un possibile errore in fase di esecuzione. Per altre informazioni, vedere [conversioni](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) verso un tipo di dati più piccolo e [istruzioni Option Strict](../statements/option-strict-statement.md).  
  
## <a name="overloading"></a>Overload  
 L' [operatore/(Visual Basic)](floating-point-division-operator.md) può essere sottoposto a *Overload*, il che significa che una classe o una struttura può ridefinire il comportamento quando un operando ha il tipo della classe o della struttura. L'overload dell' `/` operatore influiscono sul comportamento dell' `/=` operatore. Se il codice usa `/=` su una classe o una struttura che esegue l'overload di `/` , assicurarsi di comprendere il comportamento ridefinito. Per altre informazioni, vedere [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usato l' `/=` operatore per dividere una `Integer` variabile per secondo e assegnare il quoziente alla prima variabile.  
  
 [!code-vb[VbVbalrOperators#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#17)]  
  
## <a name="see-also"></a>Vedere anche

- [Operatore/(Visual Basic)](floating-point-division-operator.md)
- [\\= (Operatore)](integer-division-assignment-operator.md)
- [Operatori di assegnazione](assignment-operators.md)
- [Operatori aritmetici](arithmetic-operators.md)
- [Precedenza tra gli operatori in Visual Basic](operator-precedence.md)
- [Elenco degli operatori per funzionalità](operators-listed-by-functionality.md)
- [Istruzioni](../../programming-guide/language-features/statements.md)
