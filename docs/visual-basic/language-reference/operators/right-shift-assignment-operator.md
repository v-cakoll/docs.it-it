---
title: '>>Operatore ='
ms.date: 07/20/2015
f1_keywords:
- vb.>>=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- operator >>= [Visual Basic]
- compound assignment statements [Visual Basic]
- '>>= operator [Visual Basic]'
ms.assetid: 2bcd9abb-7a8c-4229-b75d-8816ff1dc700
ms.openlocfilehash: c3afe2bcc4b9732b5afd34df1b83eaebe707b3f5
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409296"
---
# <a name="-operator-visual-basic"></a>Operatore >>= (Visual Basic)
Esegue uno spostamento a destra aritmetico sul valore di una variabile o di una proprietà e assegna il risultato alla variabile o alla proprietà.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
variableorproperty >>= amount  
```  
  
## <a name="parts"></a>Parti  
 `variableorproperty`  
 Obbligatorio. Variabile o proprietà di un tipo integrale ( `SByte` , `Byte` , `Short` , `UShort` , `Integer` , `UInteger` , `Long` o `ULong` ).  
  
 `amount`  
 Obbligatorio. Espressione numerica di un tipo di dati che viene ampliato a `Integer` .  
  
## <a name="remarks"></a>Commenti  
 L'elemento sul lato sinistro dell' `>>=` operatore può essere una variabile scalare semplice, una proprietà o un elemento di una matrice. La variabile o la proprietà non può essere di sola [lettura](../modifiers/readonly.md).  
  
 L' `>>=` operatore esegue prima di tutto un spostamento a destra aritmetico sul valore della variabile o della proprietà. L'operatore assegna quindi il risultato dell'operazione alla variabile o alla proprietà.  
  
 I turni aritmetici non sono circolari, il che significa che i bit spostati da un'estremità del risultato non vengono reintrodotti nell'altra estremità. In uno spostamento a destra aritmetico i bit spostati oltre la posizione del bit più a destra vengono eliminati e il bit più a sinistra viene propagato nelle posizioni dei bit sgomberate a sinistra. Ciò significa che se `variableorproperty` ha un valore negativo, le posizioni sgomberate sono impostate su uno. Se `variableorproperty` è positivo o se il tipo di dati è un tipo senza segno, le posizioni sgomberate vengono impostate su zero.  
  
## <a name="overloading"></a>Overload  
 L' [operatore>> ](right-shift-operator.md) può essere sottoposto a *Overload*, il che significa che una classe o una struttura può ridefinire il comportamento quando un operando ha il tipo della classe o della struttura. L'overload dell' `>>` operatore influiscono sul comportamento dell' `>>=` operatore. Se il codice usa `>>=` su una classe o una struttura che esegue l'overload di `>>` , assicurarsi di comprendere il comportamento ridefinito. Per altre informazioni, vedere [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usato l' `>>=` operatore per spostare lo schema di bit di una `Integer` variabile a destra della quantità specificata e assegnare il risultato alla variabile.  
  
 [!code-vb[VbVbalrOperators#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#15)]  
  
## <a name="see-also"></a>Vedere anche

- [Operatore>> ](right-shift-operator.md)
- [Operatori di assegnazione](assignment-operators.md)
- [Operatori di spostamento bit](bit-shift-operators.md)
- [Precedenza tra gli operatori in Visual Basic](operator-precedence.md)
- [Elenco degli operatori per funzionalità](operators-listed-by-functionality.md)
- [Istruzioni](../../programming-guide/language-features/statements.md)
