---
title: Il primo operando in un'espressione 'If' binaria deve essere nullable o un tipo riferimento
ms.date: 07/20/2015
f1_keywords:
- bc33107
- vbc33107
helpviewer_keywords:
- BC33107
ms.assetid: 493c8899-3f6b-4471-8eb6-9284e8492768
ms.openlocfilehash: 4b520949cb59b63ea39441632dc5e2c6d000d711
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249526"
---
# <a name="first-operand-in-a-binary-if-expression-must-be-nullable-or-a-reference-type"></a>Il primo operando in un'espressione 'If' binaria deve essere nullable o un tipo riferimento
Un'espressione `If` può accettare due o tre argomenti. Quando si inviano solo due argomenti, il primo argomento deve essere un tipo di riferimento o un tipo di valore nullable. Se il primo argomento restituisce `Nothing`un valore diverso da , viene restituito il relativo valore. Se il primo argomento `Nothing`restituisce , il secondo argomento viene valutato e restituito.  
  
 Ad esempio, il codice `If` seguente contiene due espressioni, una con tre argomenti e una con due argomenti. Le espressioni calcolano e restituiscono lo stesso valore.  
  
```vb  
' firstChoice is a nullable value type.  
Dim firstChoice? As Integer = Nothing  
Dim secondChoice As Integer = 1128  
' If expression with three arguments.  
Console.WriteLine(If(firstChoice IsNot Nothing, firstChoice, secondChoice))  
' If expression with two arguments.  
Console.WriteLine(If(firstChoice, secondChoice))  
```  
  
 Le seguenti espressioni causano questo errore:  
  
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
  
- Se non è possibile modificare il codice in modo che il primo argomento sia un `If` tipo di `If...Then...Else` valore nullable o un tipo di riferimento, prendere in considerazione la conversione in un'espressione a tre argomenti o in un'istruzione.  
  
```vb  
Console.WriteLine(If(choice1 < choice2, 1, 2))  
Console.WriteLine(If(booleanVar, "Test returns True.", "Test returns False."))  
```  
  
## <a name="see-also"></a>Vedere anche

- [Operatore If](../../../visual-basic/language-reference/operators/if-operator.md)
- [Istruzione If...Then...Else](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [Tipi di valore nullableNullable Value Types](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
