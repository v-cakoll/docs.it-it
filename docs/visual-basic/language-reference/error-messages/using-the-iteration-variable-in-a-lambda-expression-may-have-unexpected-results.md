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
# <a name="using-the-iteration-variable-in-a-lambda-expression-may-have-unexpected-results"></a><span data-ttu-id="03d3f-102">L'utilizzo della variabile di iterazione in un'espressione lambda può produrre risultati imprevisti</span><span class="sxs-lookup"><span data-stu-id="03d3f-102">Using the iteration variable in a lambda expression may have unexpected results</span></span>
<span data-ttu-id="03d3f-103">Utilizzo della variabile di iterazione in un'espressione lambda può produrre risultati imprevisti.</span><span class="sxs-lookup"><span data-stu-id="03d3f-103">Using the iteration variable in a lambda expression may have unexpected results.</span></span> <span data-ttu-id="03d3f-104">In alternativa, creare una variabile locale all'interno del ciclo e assegnarvi il valore della variabile di iterazione.</span><span class="sxs-lookup"><span data-stu-id="03d3f-104">Instead, create a local variable within the loop and assign it the value of the iteration variable.</span></span>  
  
 <span data-ttu-id="03d3f-105">Questo avviso viene visualizzato quando si utilizza una variabile di iterazione del ciclo in un'espressione lambda dichiarata all'interno del ciclo.</span><span class="sxs-lookup"><span data-stu-id="03d3f-105">This warning appears when you use a loop iteration variable in a lambda expression that is declared inside the loop.</span></span> <span data-ttu-id="03d3f-106">Ad esempio, l'esempio seguente genera l'avviso venga visualizzato.</span><span class="sxs-lookup"><span data-stu-id="03d3f-106">For example, the following example causes the warning to appear.</span></span>  
  
```vb  
For i As Integer = 1 To 10  
    ' The warning is given for the use of i.  
    Dim exampleFunc As Func(Of Integer) = Function() i  
Next  
```  
  
 <span data-ttu-id="03d3f-107">Nell'esempio seguente mostra i risultati imprevisti che potrebbero verificarsi.</span><span class="sxs-lookup"><span data-stu-id="03d3f-107">The following example shows the unexpected results that might occur.</span></span>  
  
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
  
 <span data-ttu-id="03d3f-108">Il `For` ciclo crea una matrice di espressioni lambda, ognuna delle quali restituisce il valore della variabile di iterazione del ciclo `i`.</span><span class="sxs-lookup"><span data-stu-id="03d3f-108">The `For` loop creates an array of lambda expressions, each of which returns the value of the loop iteration variable `i`.</span></span> <span data-ttu-id="03d3f-109">Quando le espressioni lambda vengono valutate nel `For Each` ciclo, potrebbe essere previsti 0, 1, 2, 3 e 4, i valori successivi di `i` nel `For` ciclo.</span><span class="sxs-lookup"><span data-stu-id="03d3f-109">When the lambda expressions are evaluated in the `For Each` loop, you might expect to see 0, 1, 2, 3, and 4 displayed, the successive values of `i` in the `For` loop.</span></span> <span data-ttu-id="03d3f-110">Vedere invece il valore finale di `i` per cinque volte:</span><span class="sxs-lookup"><span data-stu-id="03d3f-110">Instead, you see the final value of `i` displayed five times:</span></span>  
  
 `5`  
  
 `5`  
  
 `5`  
  
 `5`  
  
 `5`  
  
 <span data-ttu-id="03d3f-111">Per impostazione predefinita, si tratta di un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="03d3f-111">By default, this message is a warning.</span></span> <span data-ttu-id="03d3f-112">Per ulteriori informazioni su come nascondere gli avvisi o considerarli come errori, vedere [configurazione degli avvisi in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="03d3f-112">For more information about hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="03d3f-113">**ID errore:** BC42324</span><span class="sxs-lookup"><span data-stu-id="03d3f-113">**Error ID:** BC42324</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="03d3f-114">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="03d3f-114">To correct this error</span></span>  
  
-   <span data-ttu-id="03d3f-115">Assegnare il valore della variabile di iterazione a una variabile locale e utilizzare la variabile locale nell'espressione lambda.</span><span class="sxs-lookup"><span data-stu-id="03d3f-115">Assign the value of the iteration variable to a local variable, and use the local variable in the lambda expression.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="03d3f-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="03d3f-116">See Also</span></span>  
 [<span data-ttu-id="03d3f-117">Espressioni lambda</span><span class="sxs-lookup"><span data-stu-id="03d3f-117">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
