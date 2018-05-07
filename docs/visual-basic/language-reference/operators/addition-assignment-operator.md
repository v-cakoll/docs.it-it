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
ms.openlocfilehash: f12a0560d984f871110c02f1df2c2ec42b68809b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="-operator-visual-basic"></a>Operatore += (Visual Basic)
Aggiunge il valore di un'espressione numerica per il valore di una proprietà o una variabile numerica e assegna il risultato alla variabile o proprietà. Può essere utilizzato anche per concatenare un `String` espressione da un `String` variabile o proprietà e assegnare il risultato alla variabile o proprietà.  
  
## <a name="syntax"></a>Sintassi  
  
```  
variableorproperty += expression  
```  
  
## <a name="parts"></a>Parti  
 `variableorproperty`  
 Obbligatorio. Qualsiasi numerica o `String` variabile o proprietà.  
  
 `expression`  
 Obbligatorio. Qualsiasi numerica o `String` espressione.  
  
## <a name="remarks"></a>Note  
 L'elemento sul lato sinistro del `+=` operatore può essere una semplice variabile scalare, una proprietà o un elemento della matrice. La variabile o proprietà non può essere [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
 Il `+=` operatore aggiunge il valore alla sua destra alla variabile o proprietà alla sua sinistra e assegna il risultato alla variabile o proprietà alla sua sinistra. Il `+=` operatore può essere utilizzato anche per concatenare il `String` espressione alla sua destra per il `String` variabile o proprietà relativi a sinistra e assegnare il risultato alla variabile o proprietà alla sua sinistra.  
  
> [!NOTE]
>  Quando si utilizza il `+=` operatore, potrebbe non essere in grado di determinare se verrà eseguita la concatenazione di addizione o stringa. Utilizzare il `&=` operatore per la concatenazione per evitare ambiguità e fornire codice autodocumentato.  
  
 L'operatore di assegnazione esegue, in modo implicito, ma non le conversioni di restrizione se l'ambiente di compilazione viene applicata una semantica di ampliamento. Per ulteriori informazioni sulle conversioni, vedere [conversioni di ampliamento e restrizione](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md). Per ulteriori informazioni sulla semantica rigida e permissiva, vedere [istruzione Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md).  
  
 Se la semantica permissiva è consentita, la `+=` operatore esegue in modo implicito una serie di conversioni di stringa e numerici identiche a quelli eseguiti dal `+` operatore. Per informazioni dettagliate su queste conversioni, vedere [+ (operatore)](../../../visual-basic/language-reference/operators/addition-operator.md).  
  
## <a name="overloading"></a>Overload  
 Il `+` operatore può essere *overload*, il che significa che una classe o struttura ridefinire il comportamento quando un operando ha il tipo di quella classe o struttura. L'overload di `+` operatore influisce sul comportamento del `+=` operatore. Se il codice utilizza `+=` in una classe o struttura che esegue l'overload `+`, assicurarsi di comprendere il comportamento ridefinito. Per ulteriori informazioni, vedere [routine di operatore](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il `+=` operatore per combinare il valore di una variabile con un altro. La prima parte Usa `+=` con le variabili numeriche per aggiungere un valore a un altro. Utilizza la seconda parte `+=` con `String` variabili per concatenare due valori con un altro. In entrambi i casi, il risultato viene assegnato alla prima variabile.  
  
 [!code-vb[VbVbalrOperators#7](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-assignment-operator_1.vb)]  
  
 [!code-vb[VbVbalrOperators#8](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-assignment-operator_2.vb)]  
  
 Il valore di `num1` è ora 13 e il valore di `str1` è ora "103".  
  
## <a name="see-also"></a>Vedere anche  
 [Operatore +](../../../visual-basic/language-reference/operators/addition-operator.md)  
 [Operatori di assegnazione](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [Operatori aritmetici](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [Operatori di concatenazione](../../../visual-basic/language-reference/operators/concatenation-operators.md)  
 [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Istruzioni](../../../visual-basic/programming-guide/language-features/statements.md)
