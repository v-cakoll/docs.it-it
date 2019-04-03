---
title: L'utilizzo della variabile di iterazione in un'espressione lambda può produrre risultati imprevisti
ms.date: 07/20/2015
f1_keywords:
- vbc42324
- bc42324
helpviewer_keywords:
- BC42324
ms.assetid: b5c2c4bd-3b2a-4a73-aaeb-55728eb03b68
ms.openlocfilehash: 618fc88a2ca92ec911a3fbd82de580403d924430
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58841100"
---
# <a name="using-the-iteration-variable-in-a-lambda-expression-may-have-unexpected-results"></a>L'utilizzo della variabile di iterazione in un'espressione lambda può produrre risultati imprevisti
Uso della variabile di iterazione in un'espressione lambda può produrre risultati imprevisti. In alternativa, creare una variabile locale all'interno del ciclo e assegnare il valore della variabile di iterazione.  
  
 Questo avviso viene visualizzato quando si usa una variabile di iterazione del ciclo in un'espressione lambda dichiarata all'interno del ciclo. Ad esempio, l'esempio seguente genera l'avviso venga visualizzato.  
  
```vb  
For i As Integer = 1 To 10  
    ' The warning is given for the use of i.  
    Dim exampleFunc As Func(Of Integer) = Function() i  
Next  
```  
  
 Nell'esempio seguente mostra i risultati imprevisti che potrebbero verificarsi.  
  
```vb  
Module Module1  
    Sub Main()  
        Dim array1 As Func(Of Integer)() = New Func(Of Integer)(4) {}  
  
        For i As Integer = 0 To 4  
            array1(i) = Function() i  
        Next  
  
        For Each funcElement In array1  
            System.Console.WriteLine(funcElement())  
        Next  
  
    End Sub  
End Module  
```  
  
 Il `For` ciclo crea una matrice di espressioni lambda, ognuna delle quali restituisce il valore della variabile di iterazione del ciclo `i`. Quando vengono valutate le espressioni lambda nel `For Each` ciclo, si aspetterebbe di vedere 0, 1, 2, 3 e 4, i valori successivi di `i` nel `For` ciclo. Vedere invece il valore finale della `i` visualizzate cinque volte:  
  
 `5`  
  
 `5`  
  
 `5`  
  
 `5`  
  
 `5`  
  
 Per impostazione predefinita, si tratta di un messaggio di avviso. Per altre informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **ID errore:** BC42324  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Assegnare il valore della variabile di iterazione a una variabile locale e usare la variabile locale nell'espressione lambda.  
  
```vb  
Module Module1  
    Sub Main()  
        Dim array1 As Func(Of Integer)() = New Func(Of Integer)(4) {}  
  
        For i As Integer = 0 To 4  
            Dim j = i  
            array1(i) = Function() j  
        Next  
  
        For Each funcElement In array1  
            System.Console.WriteLine(funcElement())  
        Next  
  
    End Sub  
End Module  
```  
  
## <a name="see-also"></a>Vedere anche

- [Espressioni lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
