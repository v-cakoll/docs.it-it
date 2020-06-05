---
title: L'utilizzo della variabile di iterazione in un'espressione lambda può produrre risultati imprevisti
ms.date: 07/20/2015
f1_keywords:
- vbc42324
- bc42324
helpviewer_keywords:
- BC42324
ms.assetid: b5c2c4bd-3b2a-4a73-aaeb-55728eb03b68
ms.openlocfilehash: aa3e1d6281af22b301a4697b265ed3fbf23e3de4
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84373914"
---
# <a name="using-the-iteration-variable-in-a-lambda-expression-may-have-unexpected-results"></a>L'utilizzo della variabile di iterazione in un'espressione lambda può produrre risultati imprevisti
L'uso della variabile di iterazione in un'espressione lambda può produrre risultati imprevisti. Al contrario, creare una variabile locale all'interno del ciclo e assegnarle il valore della variabile di iterazione.  
  
 Questo avviso viene visualizzato quando si usa una variabile di iterazione del ciclo in un'espressione lambda dichiarata all'interno del ciclo. Nell'esempio seguente, ad esempio, viene visualizzato l'avviso.  
  
```vb  
For i As Integer = 1 To 10  
    ' The warning is given for the use of i.  
    Dim exampleFunc As Func(Of Integer) = Function() i  
Next  
```  
  
 Nell'esempio seguente vengono illustrati i risultati imprevisti che possono verificarsi.  
  
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
  
 Il `For` ciclo crea una matrice di espressioni lambda, ciascuna delle quali restituisce il valore della variabile di iterazione del ciclo `i` . Quando le espressioni lambda vengono valutate nel `For Each` ciclo, è possibile che vengano visualizzati 0, 1, 2, 3 e 4, ovvero i valori successivi del `i` `For` ciclo. Viene invece visualizzato il valore finale di `i` cinque volte:  
  
 `5`  
  
 `5`  
  
 `5`  
  
 `5`  
  
 `5`  
  
 Per impostazione predefinita, si tratta di un messaggio di avviso. Per altre informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **ID errore:** BC42324  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Assegnare il valore della variabile di iterazione a una variabile locale e usare la variabile locale nell'espressione lambda.  
  
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

- [Espressioni lambda](../../programming-guide/language-features/procedures/lambda-expressions.md)
