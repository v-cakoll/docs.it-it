---
title: Il primo operando in un file binario &#39;se&#39; espressione deve essere nullable o un tipo di riferimento
ms.date: 07/20/2015
f1_keywords:
- bc33107
- vbc33107
helpviewer_keywords:
- BC33107
ms.assetid: 493c8899-3f6b-4471-8eb6-9284e8492768
ms.openlocfilehash: 76078d315b2c32a2a29aa652a65b463622afec36
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33590829"
---
# <a name="first-operand-in-a-binary-39if39-expression-must-be-nullable-or-a-reference-type"></a>Il primo operando in un file binario &#39;se&#39; espressione deve essere nullable o un tipo di riferimento
Un `If` espressione può accettare due o tre argomenti. Quando si inviano solo due argomenti, il primo argomento deve essere un tipo riferimento o un tipo nullable. Se il primo argomento restituisce un valore diverso da `Nothing`, viene restituito il relativo valore. Se il primo argomento restituisce `Nothing`verrà restituito il secondo argomento.  
  
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
  
 Le espressioni seguenti motivi:  
  
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
  
-   Se è possibile modificare il codice in modo che il primo argomento è un tipo nullable o un tipo riferimento, eseguire la conversione a un argomento di tre `If` espressione, o a un `If...Then...Else` istruzione.  
  
```vb  
Console.WriteLine(If(choice1 < choice2, 1, 2))  
Console.WriteLine(If(booleanVar, "Test returns True.", "Test returns False."))  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Operatore If](../../../visual-basic/language-reference/operators/if-operator.md)  
 [Istruzione If...Then...Else](../../../visual-basic/language-reference/statements/if-then-else-statement.md)  
 [Tipi di valori nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
