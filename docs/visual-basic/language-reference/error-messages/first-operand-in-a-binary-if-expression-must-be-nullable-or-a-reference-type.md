---
title: Il primo operando in un'espressione 'If' binaria deve essere nullable o un tipo riferimento
ms.date: 07/20/2015
f1_keywords:
- bc33107
- vbc33107
helpviewer_keywords:
- BC33107
ms.assetid: 493c8899-3f6b-4471-8eb6-9284e8492768
ms.openlocfilehash: ca16c6604ee071668a5c65d7e9052b233e2313c7
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403018"
---
# <a name="first-operand-in-a-binary-if-expression-must-be-nullable-or-a-reference-type"></a>Il primo operando in un'espressione 'If' binaria deve essere nullable o un tipo riferimento
Un' `If` espressione può assumere due o tre argomenti. Quando si inviano solo due argomenti, il primo argomento deve essere un tipo di riferimento o un tipo di valore Nullable. Se il primo argomento restituisce qualcosa di diverso da `Nothing` , viene restituito il relativo valore. Se il primo argomento restituisce `Nothing` , il secondo argomento viene valutato e restituito.  
  
 Il codice seguente, ad esempio, contiene due `If` espressioni, una con tre argomenti e una con due argomenti. Le espressioni calcolano e restituiscono lo stesso valore.  
  
```vb  
' firstChoice is a nullable value type.  
Dim firstChoice? As Integer = Nothing  
Dim secondChoice As Integer = 1128  
' If expression with three arguments.  
Console.WriteLine(If(firstChoice IsNot Nothing, firstChoice, secondChoice))  
' If expression with two arguments.  
Console.WriteLine(If(firstChoice, secondChoice))  
```  
  
 Le seguenti espressioni generano questo errore:  
  
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
  
- Se non è possibile modificare il codice in modo che il primo argomento sia un tipo di valore o un tipo di riferimento Nullable, provare a eseguire la conversione in un'espressione a tre argomenti `If` o in un' `If...Then...Else` istruzione.  
  
```vb  
Console.WriteLine(If(choice1 < choice2, 1, 2))  
Console.WriteLine(If(booleanVar, "Test returns True.", "Test returns False."))  
```  
  
## <a name="see-also"></a>Vedere anche

- [Operatore If](../operators/if-operator.md)
- [Istruzione If...Then...Else](../statements/if-then-else-statement.md)
- [Tipi di valore Nullable](../../programming-guide/language-features/data-types/nullable-value-types.md)
