---
title: "Utilizzo la variabile di iterazione in un&quot;espressione lambda può produrre risultati imprevisti | Documenti di Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc42324
- bc42324
dev_langs:
- VB
helpviewer_keywords:
- BC42324
ms.assetid: b5c2c4bd-3b2a-4a73-aaeb-55728eb03b68
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 1c2e0e322ff46b9e215a169cd4cf3805c7dc3943
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="using-the-iteration-variable-in-a-lambda-expression-may-have-unexpected-results"></a><span data-ttu-id="66fe7-102">L'utilizzo della variabile di iterazione in un'espressione lambda può produrre risultati imprevisti</span><span class="sxs-lookup"><span data-stu-id="66fe7-102">Using the iteration variable in a lambda expression may have unexpected results</span></span>
<span data-ttu-id="66fe7-103">L'uso della variabile di iterazione in un'espressione lambda può produrre risultati imprevisti.</span><span class="sxs-lookup"><span data-stu-id="66fe7-103">Using the iteration variable in a lambda expression may have unexpected results.</span></span> <span data-ttu-id="66fe7-104">In alternativa, creare una variabile locale all'interno del ciclo e viene assegnato il valore della variabile di iterazione.</span><span class="sxs-lookup"><span data-stu-id="66fe7-104">Instead, create a local variable within the loop and assign it the value of the iteration variable.</span></span>  
  
 <span data-ttu-id="66fe7-105">Questo avviso viene visualizzato quando si utilizza una variabile di iterazione del ciclo in un'espressione lambda che viene dichiarata all'interno del ciclo.</span><span class="sxs-lookup"><span data-stu-id="66fe7-105">This warning appears when you use a loop iteration variable in a lambda expression that is declared inside the loop.</span></span> <span data-ttu-id="66fe7-106">Ad esempio, l'esempio seguente genera questo avviso.</span><span class="sxs-lookup"><span data-stu-id="66fe7-106">For example, the following example causes the warning to appear.</span></span>  
  
```vb  
For i As Integer = 1 To 10  
    ' The warning is given for the use of i.  
    Dim exampleFunc As Func(Of Integer) = Function() i  
Next  
```  
  
 <span data-ttu-id="66fe7-107">Nell'esempio seguente viene illustrato che potrebbero verificarsi risultati imprevisti.</span><span class="sxs-lookup"><span data-stu-id="66fe7-107">The following example shows the unexpected results that might occur.</span></span>  
  
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
  
 <span data-ttu-id="66fe7-108">Il `For` ciclo crea una matrice di espressioni lambda, ognuna delle quali restituisce il valore della variabile di iterazione del ciclo `i`.</span><span class="sxs-lookup"><span data-stu-id="66fe7-108">The `For` loop creates an array of lambda expressions, each of which returns the value of the loop iteration variable `i`.</span></span> <span data-ttu-id="66fe7-109">Quando vengono valutate le espressioni lambda nel `For Each` ciclo, si aspetterebbe di vedere 0, 1, 2, 3 e 4, i valori successivi di `i` nel `For` ciclo.</span><span class="sxs-lookup"><span data-stu-id="66fe7-109">When the lambda expressions are evaluated in the `For Each` loop, you might expect to see 0, 1, 2, 3, and 4 displayed, the successive values of `i` in the `For` loop.</span></span> <span data-ttu-id="66fe7-110">Vedere invece il valore finale del `i` per cinque volte:</span><span class="sxs-lookup"><span data-stu-id="66fe7-110">Instead, you see the final value of `i` displayed five times:</span></span>  
  
 `5`  
  
 `5`  
  
 `5`  
  
 `5`  
  
 `5`  
  
 <span data-ttu-id="66fe7-111">Per impostazione predefinita, si tratta di un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="66fe7-111">By default, this message is a warning.</span></span> <span data-ttu-id="66fe7-112">Per ulteriori informazioni su come nascondere gli avvisi o considerarli come errori, vedere [configurazione degli avvisi in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="66fe7-112">For more information about hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="66fe7-113">**ID errore:** BC42324</span><span class="sxs-lookup"><span data-stu-id="66fe7-113">**Error ID:** BC42324</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="66fe7-114">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="66fe7-114">To correct this error</span></span>  
  
-   <span data-ttu-id="66fe7-115">Assegnare il valore della variabile di iterazione a una variabile locale e utilizzare la variabile locale nell'espressione lambda.</span><span class="sxs-lookup"><span data-stu-id="66fe7-115">Assign the value of the iteration variable to a local variable, and use the local variable in the lambda expression.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="66fe7-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="66fe7-116">See Also</span></span>  
 [<span data-ttu-id="66fe7-117">Espressioni lambda</span><span class="sxs-lookup"><span data-stu-id="66fe7-117">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
