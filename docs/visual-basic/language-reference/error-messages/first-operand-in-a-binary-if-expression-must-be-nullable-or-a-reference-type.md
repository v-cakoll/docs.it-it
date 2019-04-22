---
title: Il primo operando in un'espressione 'If' binaria deve essere nullable o un tipo riferimento
ms.date: 07/20/2015
f1_keywords:
- bc33107
- vbc33107
helpviewer_keywords:
- BC33107
ms.assetid: 493c8899-3f6b-4471-8eb6-9284e8492768
ms.openlocfilehash: 32ff0adca9d35e6b5439ae06be85414924dac2e6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58838625"
---
# <a name="first-operand-in-a-binary-if-expression-must-be-nullable-or-a-reference-type"></a>Il primo operando in un'espressione 'If' binaria deve essere nullable o un tipo riferimento
Un `If` espressione può avere due o tre argomenti. Quando si inviano solo due argomenti, il primo argomento deve essere un tipo riferimento o un tipo nullable. Se il primo argomento restituisce un valore diverso da `Nothing`, viene restituito il relativo valore. Se il primo argomento restituisce `Nothing`, il secondo argomento viene valutato e restituito.  
  
 Ad esempio, il codice seguente contiene due `If` espressioni, uno con tre argomenti e uno con due argomenti. Le espressioni di calcolare e restituiscono lo stesso valore.  
  
```vb  
' firstChoice is a nullable value type.  
Dim firstChoice? As Integer = Nothing  
Dim secondChoice As Integer = 1128  
' If expression with three arguments.  
Console.WriteLine(If(firstChoice IsNot Nothing, firstChoice, secondChoice))  
' If expression with two arguments.  
Console.WriteLine(If(firstChoice, secondChoice))  
```  
  
 Questo errore è causato da espressioni seguenti:  
  
```vb  
Dim choice1 = 4  
Dim choice2 = 5  
Dim booleanVar = True  
  
' Not valid.  
'Console.WriteLine(If(choice1 < choice2, 1))  
' Not valid.  
'Console.WriteLine(If(booleanVar, "Test returns True."))  
```  
  
 **ID errore:** BC33107  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Se è possibile modificare il codice in modo che il primo argomento è un tipo che ammette valori null o un tipo riferimento, eseguire la conversione a un argomento di tre `If` expression, o a un `If...Then...Else` istruzione.  
  
```vb  
Console.WriteLine(If(choice1 < choice2, 1, 2))  
Console.WriteLine(If(booleanVar, "Test returns True.", "Test returns False."))  
```  
  
## <a name="see-also"></a>Vedere anche

- [Operatore If](../../../visual-basic/language-reference/operators/if-operator.md)
- [Istruzione If...Then...Else](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [Tipi di valori nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
