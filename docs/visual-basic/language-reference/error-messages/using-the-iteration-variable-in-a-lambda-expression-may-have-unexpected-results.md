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
# <a name="using-the-iteration-variable-in-a-lambda-expression-may-have-unexpected-results"></a><span data-ttu-id="7bdaa-102">L'utilizzo della variabile di iterazione in un'espressione lambda può produrre risultati imprevisti</span><span class="sxs-lookup"><span data-stu-id="7bdaa-102">Using the iteration variable in a lambda expression may have unexpected results</span></span>
<span data-ttu-id="7bdaa-103">L'uso della variabile di iterazione in un'espressione lambda può produrre risultati imprevisti.</span><span class="sxs-lookup"><span data-stu-id="7bdaa-103">Using the iteration variable in a lambda expression may have unexpected results.</span></span> <span data-ttu-id="7bdaa-104">Al contrario, creare una variabile locale all'interno del ciclo e assegnarle il valore della variabile di iterazione.</span><span class="sxs-lookup"><span data-stu-id="7bdaa-104">Instead, create a local variable within the loop and assign it the value of the iteration variable.</span></span>  
  
 <span data-ttu-id="7bdaa-105">Questo avviso viene visualizzato quando si usa una variabile di iterazione del ciclo in un'espressione lambda dichiarata all'interno del ciclo.</span><span class="sxs-lookup"><span data-stu-id="7bdaa-105">This warning appears when you use a loop iteration variable in a lambda expression that is declared inside the loop.</span></span> <span data-ttu-id="7bdaa-106">Nell'esempio seguente, ad esempio, viene visualizzato l'avviso.</span><span class="sxs-lookup"><span data-stu-id="7bdaa-106">For example, the following example causes the warning to appear.</span></span>  
  
```vb  
For i As Integer = 1 To 10  
    ' The warning is given for the use of i.  
    Dim exampleFunc As Func(Of Integer) = Function() i  
Next  
```  
  
 <span data-ttu-id="7bdaa-107">Nell'esempio seguente vengono illustrati i risultati imprevisti che possono verificarsi.</span><span class="sxs-lookup"><span data-stu-id="7bdaa-107">The following example shows the unexpected results that might occur.</span></span>  
  
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
  
 <span data-ttu-id="7bdaa-108">Il `For` ciclo crea una matrice di espressioni lambda, ciascuna delle quali restituisce il valore della variabile di iterazione del ciclo `i` .</span><span class="sxs-lookup"><span data-stu-id="7bdaa-108">The `For` loop creates an array of lambda expressions, each of which returns the value of the loop iteration variable `i`.</span></span> <span data-ttu-id="7bdaa-109">Quando le espressioni lambda vengono valutate nel `For Each` ciclo, è possibile che vengano visualizzati 0, 1, 2, 3 e 4, ovvero i valori successivi del `i` `For` ciclo.</span><span class="sxs-lookup"><span data-stu-id="7bdaa-109">When the lambda expressions are evaluated in the `For Each` loop, you might expect to see 0, 1, 2, 3, and 4 displayed, the successive values of `i` in the `For` loop.</span></span> <span data-ttu-id="7bdaa-110">Viene invece visualizzato il valore finale di `i` cinque volte:</span><span class="sxs-lookup"><span data-stu-id="7bdaa-110">Instead, you see the final value of `i` displayed five times:</span></span>  
  
 `5`  
  
 `5`  
  
 `5`  
  
 `5`  
  
 `5`  
  
 <span data-ttu-id="7bdaa-111">Per impostazione predefinita, si tratta di un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="7bdaa-111">By default, this message is a warning.</span></span> <span data-ttu-id="7bdaa-112">Per altre informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="7bdaa-112">For more information about hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="7bdaa-113">**ID errore:** BC42324</span><span class="sxs-lookup"><span data-stu-id="7bdaa-113">**Error ID:** BC42324</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7bdaa-114">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="7bdaa-114">To correct this error</span></span>  
  
- <span data-ttu-id="7bdaa-115">Assegnare il valore della variabile di iterazione a una variabile locale e usare la variabile locale nell'espressione lambda.</span><span class="sxs-lookup"><span data-stu-id="7bdaa-115">Assign the value of the iteration variable to a local variable, and use the local variable in the lambda expression.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7bdaa-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7bdaa-116">See also</span></span>

- [<span data-ttu-id="7bdaa-117">Espressioni lambda</span><span class="sxs-lookup"><span data-stu-id="7bdaa-117">Lambda Expressions</span></span>](../../programming-guide/language-features/procedures/lambda-expressions.md)
