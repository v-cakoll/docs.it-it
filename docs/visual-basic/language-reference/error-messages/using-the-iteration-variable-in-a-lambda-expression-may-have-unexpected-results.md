---
title: L'utilizzo della variabile di iterazione in un'espressione lambda può produrre risultati imprevisti
ms.date: 07/20/2015
f1_keywords:
- vbc42324
- bc42324
helpviewer_keywords:
- BC42324
ms.assetid: b5c2c4bd-3b2a-4a73-aaeb-55728eb03b68
ms.openlocfilehash: 7144a5fd4a197fddaf1ac4132df0ff70995ad067
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33594162"
---
# <a name="using-the-iteration-variable-in-a-lambda-expression-may-have-unexpected-results"></a>L'utilizzo della variabile di iterazione in un'espressione lambda può produrre risultati imprevisti
Utilizzo della variabile di iterazione in un'espressione lambda può produrre risultati imprevisti. In alternativa, creare una variabile locale all'interno del ciclo e assegnarvi il valore della variabile di iterazione.  
  
 Questo avviso viene visualizzato quando si utilizza una variabile di iterazione del ciclo in un'espressione lambda dichiarata all'interno del ciclo. Ad esempio, l'esempio seguente genera l'avviso venga visualizzato.  
  
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
  
 Il `For` ciclo crea una matrice di espressioni lambda, ognuna delle quali restituisce il valore della variabile di iterazione del ciclo `i`. Quando le espressioni lambda vengono valutate nel `For Each` ciclo, potrebbe essere previsti 0, 1, 2, 3 e 4, i valori successivi di `i` nel `For` ciclo. Vedere invece il valore finale di `i` per cinque volte:  
  
 `5`  
  
 `5`  
  
 `5`  
  
 `5`  
  
 `5`  
  
 Per impostazione predefinita, si tratta di un messaggio di avviso. Per ulteriori informazioni su come nascondere gli avvisi o considerarli come errori, vedere [configurazione degli avvisi in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **ID errore:** BC42324  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Assegnare il valore della variabile di iterazione a una variabile locale e utilizzare la variabile locale nell'espressione lambda.  
  
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
 [Espressioni lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
