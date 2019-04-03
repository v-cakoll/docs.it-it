---
title: Operatore += (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.+=
helpviewer_keywords:
- += operator [Visual Basic]
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- += operator [Visual Basic], appending strings
- compound assignment statements [Visual Basic]
ms.assetid: d3e959f4-85d4-4e47-87c4-77b62335a5b3
ms.openlocfilehash: 4b8f36397d0f52866ebe9fa188d6b163364aeffc
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58839016"
---
# <a name="-operator-visual-basic"></a>Operatore += (Visual Basic)
Aggiunge il valore di un'espressione numerica per il valore di una proprietà o variabile numerica e assegna il risultato alla variabile o proprietà. Può anche essere utilizzato per concatenare un' `String` espressione da un `String` variabile o proprietà e assegna il risultato alla variabile o proprietà.  
  
## <a name="syntax"></a>Sintassi  
  
```  
variableorproperty += expression  
```  
  
## <a name="parts"></a>Parti  
 `variableorproperty`  
 Obbligatorio. Qualsiasi numerica o `String` variabile o una proprietà.  
  
 `expression`  
 Obbligatorio. Qualsiasi numerica o `String` espressione.  
  
## <a name="remarks"></a>Note  
 L'elemento sul lato sinistro del `+=` operatore può essere una variabile semplice scalare, una proprietà o un elemento della matrice. La variabile o proprietà non può essere [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
 Il `+=` operatore aggiunge il valore alla sua destra per la variabile o una proprietà alla sua sinistra e assegna il risultato alla variabile o proprietà alla sua sinistra. Il `+=` operatore può essere utilizzato anche per concatenare le `String` espressione alla sua destra per il `String` variabile o proprietà a sinistra e le assegna il risultato alla variabile o una proprietà alla sua sinistra.  
  
> [!NOTE]
>  Quando si usa il `+=` operatore, potrebbe non essere in grado di determinare se verrà eseguita la concatenazione di aggiunta o la stringa. Usare il `&=` operatore per la concatenazione per evitare ambiguità e fornire codice autodocumentato.  
  
 L'operatore di assegnazione esegue in modo implicito di ampliamento ma non delle conversioni di narrowing se l'ambiente di compilazione impone la semantica rigorosa. Per altre informazioni sulle conversioni, vedere [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md). Per altre informazioni sulla semantica rigida e permissiva, vedere [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).  
  
 Se la semantica permissiva è consentita, il `+=` operatore esegue in modo implicito una serie di conversioni di stringa e numeriche identiche a quelli eseguiti dal `+` operatore. Per informazioni dettagliate su queste conversioni, vedere [operatore +](../../../visual-basic/language-reference/operators/addition-operator.md).  
  
## <a name="overloading"></a>Overload  
 Il `+` operatore può essere *sottoposto a overload*, il che significa che una classe o struttura può ridefinire il comportamento quando un operando ha il tipo di quella classe o struttura. L'overload di `+` operatore influisce sul comportamento del `+=` operatore. Se il codice usi `+=` in una classe o struttura che esegue l'overload `+`, assicurarsi di comprendere il comportamento ridefinito. Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il `+=` operatore combinare il valore di una variabile con un altro. La prima parte Usa `+=` alle variabili numeriche per aggiungere un valore a un altro. Usa la seconda parte `+=` con `String` variabili per concatenare due valori con un altro. In entrambi i casi, il risultato viene assegnato alla prima variabile.  
  
 [!code-vb[VbVbalrOperators#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#7)]  
  
 [!code-vb[VbVbalrOperators#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#8)]  
  
 Il valore di `num1` è ora 13 e il valore di `str1` è ora "103".  
  
## <a name="see-also"></a>Vedere anche

- [Operatore +](../../../visual-basic/language-reference/operators/addition-operator.md)
- [Operatori di assegnazione](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [Operatori aritmetici](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Operatori di concatenazione](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Istruzioni](../../../visual-basic/programming-guide/language-features/statements.md)
