---
title: Operatore <<=
ms.date: 07/20/2015
f1_keywords:
- vb.<<=
helpviewer_keywords:
- operator <<=
- assignment statements [Visual Basic], compound
- <<= operator [Visual Basic]
- statements [Visual Basic], compound assignment
- operator<<=
- compound assignment statements [Visual Basic]
ms.assetid: 8ad26613-faff-4e2f-89ee-63feee33bfda
ms.openlocfilehash: cc89e0dadc7148b21e695a53a2e746a00ed66441
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350948"
---
# <a name="-operator-visual-basic"></a>Operatore \<\<= (Visual Basic)
Esegue uno scorrimento a sinistra aritmetico sul valore di una variabile o di una proprietà e assegna il risultato alla variabile o alla proprietà.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
variableorproperty <<= amount  
```  
  
## <a name="parts"></a>Parti  
 `variableorproperty`  
 Obbligatoria. Variabile o proprietà di un tipo integrale (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`o `ULong`).  
  
 `amount`  
 Obbligatoria. Espressione numerica di un tipo di dati che viene ampliato a `Integer`.  
  
## <a name="remarks"></a>Note  
 L'elemento sul lato sinistro dell'operatore `<<=` può essere una variabile scalare semplice, una proprietà o un elemento di una matrice. La variabile o la proprietà non può essere di sola [lettura](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
 L'operatore `<<=` esegue innanzitutto uno spostamento a sinistra aritmetico sul valore della variabile o della proprietà. L'operatore assegna quindi il risultato dell'operazione alla variabile o alla proprietà.  
  
 I turni aritmetici non sono circolari, il che significa che i bit spostati da un'estremità del risultato non vengono reintrodotti nell'altra estremità. In uno scorrimento a sinistra aritmetico, i bit spostati oltre l'intervallo del tipo di dati del risultato vengono rimossi e le posizioni dei bit sgomberate a destra vengono impostate su zero.  
  
## <a name="overloading"></a>Overload  
 L' [operatore < <](../../../visual-basic/language-reference/operators/left-shift-operator.md) può essere sottoposto a *Overload*, il che significa che una classe o una struttura può ridefinire il comportamento quando un operando ha il tipo della classe o della struttura. L'overload dell'operatore `<<` influiscono sul comportamento dell'operatore `<<=`. Se il codice USA `<<=` su una classe o una struttura che esegue l'overload di `<<`, assicurarsi di comprendere il comportamento ridefinito. Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usato l'operatore `<<=` per spostare lo schema di bit di una variabile `Integer` a sinistra della quantità specificata e assegnare il risultato alla variabile.  
  
 [!code-vb[VbVbalrOperators#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#13)]  
  
## <a name="see-also"></a>Vedere anche

- [Operatore <<](../../../visual-basic/language-reference/operators/left-shift-operator.md)
- [Operatori di assegnazione](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [Operatori di spostamento bit](../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Istruzioni](../../../visual-basic/programming-guide/language-features/statements.md)
