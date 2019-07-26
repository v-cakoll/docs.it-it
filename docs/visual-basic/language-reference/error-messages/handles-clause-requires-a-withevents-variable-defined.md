---
title: La clausola Handles richiede una variabile WithEvents definita nel tipo che la contiene o in uno dei relativi tipi di base
ms.date: 07/20/2015
f1_keywords:
- vbc30506
- bc30506
helpviewer_keywords:
- BC30506
ms.assetid: 5b66f6a8-f050-4e03-a57f-a64e85f80cb5
ms.openlocfilehash: 04c94d3d32660d1a186a9bb377c49a53e1451be6
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/26/2019
ms.locfileid: "68512738"
---
# <a name="handles-clause-requires-a-withevents-variable-defined-in-the-containing-type-or-one-of-its-base-types"></a><span data-ttu-id="1d9f1-102">La clausola Handles richiede una variabile WithEvents definita nel tipo che la contiene o in uno dei relativi tipi di base</span><span class="sxs-lookup"><span data-stu-id="1d9f1-102">Handles clause requires a WithEvents variable defined in the containing type or one of its base types</span></span>
<span data-ttu-id="1d9f1-103">Non è stata fornita una `WithEvents` variabile `Handles` nella clausola.</span><span class="sxs-lookup"><span data-stu-id="1d9f1-103">You did not supply a `WithEvents` variable in your `Handles` clause.</span></span> <span data-ttu-id="1d9f1-104">La `Handles` parola chiave alla fine di una dichiarazione di routine fa in modo che gestisca gli eventi generati da una variabile `WithEvents` oggetto dichiarata con la parola chiave.</span><span class="sxs-lookup"><span data-stu-id="1d9f1-104">The `Handles` keyword at the end of a procedure declaration causes it to handle events raised by an object variable declared using the `WithEvents` keyword.</span></span>
  
 <span data-ttu-id="1d9f1-105">**ID errore:** BC30506</span><span class="sxs-lookup"><span data-stu-id="1d9f1-105">**Error ID:** BC30506</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="1d9f1-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="1d9f1-106">To correct this error</span></span>
  
- <span data-ttu-id="1d9f1-107">Specificare la variabile `WithEvents` necessaria.</span><span class="sxs-lookup"><span data-stu-id="1d9f1-107">Supply the necessary `WithEvents` variable.</span></span>
  
## <a name="example"></a><span data-ttu-id="1d9f1-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="1d9f1-108">Example</span></span>

<span data-ttu-id="1d9f1-109">Nell'esempio seguente Visual Basic genera un errore `BC30506` del compilatore perché la parola chiave [WithEvents](../modifiers/withevents.md) non viene utilizzata nella definizione dell' <xref:System.Timers.Timer?displayProperty=nameWithType> istanza.</span><span class="sxs-lookup"><span data-stu-id="1d9f1-109">In the following example, Visual Basic generates compiler error `BC30506` because the [WithEvents](../modifiers/withevents.md) keyword is not used in the definition of the <xref:System.Timers.Timer?displayProperty=nameWithType> instance.</span></span>

```vb
Imports System.Timers

Module Module1
    Private _timer1 As New Timer() With {.Interval = 1000, .Enabled = True}
    
    Sub Main()
        Console.WriteLine("Press any key to start the timer...")
        Console.ReadKey()
        _timer1.Start()
        Console.ReadKey()
    End Sub

    Private Sub Timer1_Tick(sender As Object, args As EventArgs) Handles _timer1.Elapsed
        Console.WriteLine("Press any key to terminate...")
    End Sub
End Module
```

<span data-ttu-id="1d9f1-110">L'esempio seguente viene compilato correttamente perché la `_timer1` variabile è definita con la `WithEvents` parola chiave:</span><span class="sxs-lookup"><span data-stu-id="1d9f1-110">The following example compiles successfully because the `_timer1` variable is defined with the `WithEvents` keyword:</span></span>

```vb
Imports System.Timers

Module Module1
    Private WithEvents _timer1 As New Timer() With {.Interval = 1000}

    Sub Main()
        Console.WriteLine("Press any key to start the timer...")
        Console.ReadKey()
        _timer1.Start()
        Console.ReadKey()
    End Sub

    Private Sub Timer1_Tick(sender As Object, args As EventArgs) Handles _timer1.Elapsed
        Console.WriteLine("Press any key to terminate...")
    End Sub

End Module
```

## <a name="see-also"></a><span data-ttu-id="1d9f1-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1d9f1-111">See also</span></span>

- [<span data-ttu-id="1d9f1-112">Handles</span><span class="sxs-lookup"><span data-stu-id="1d9f1-112">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)
