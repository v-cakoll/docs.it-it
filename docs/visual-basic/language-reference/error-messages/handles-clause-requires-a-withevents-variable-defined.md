---
title: La clausola Handles richiede una variabile WithEvents definita nel tipo che la contiene o in uno dei relativi tipi di base
ms.date: 07/20/2015
f1_keywords:
- vbc30506
- bc30506
helpviewer_keywords:
- BC30506
ms.assetid: 5b66f6a8-f050-4e03-a57f-a64e85f80cb5
ms.openlocfilehash: 94c4229d4036382e344cffb09295e218642c55d4
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402901"
---
# <a name="handles-clause-requires-a-withevents-variable-defined-in-the-containing-type-or-one-of-its-base-types"></a><span data-ttu-id="0eede-102">La clausola Handles richiede una variabile WithEvents definita nel tipo che la contiene o in uno dei relativi tipi di base</span><span class="sxs-lookup"><span data-stu-id="0eede-102">Handles clause requires a WithEvents variable defined in the containing type or one of its base types</span></span>

<span data-ttu-id="0eede-103">Non è stata fornita una `WithEvents` variabile nella `Handles` clausola.</span><span class="sxs-lookup"><span data-stu-id="0eede-103">You did not supply a `WithEvents` variable in your `Handles` clause.</span></span> <span data-ttu-id="0eede-104">La `Handles` parola chiave alla fine di una dichiarazione di routine fa in modo che gestisca gli eventi generati da una variabile oggetto dichiarata con la `WithEvents` parola chiave.</span><span class="sxs-lookup"><span data-stu-id="0eede-104">The `Handles` keyword at the end of a procedure declaration causes it to handle events raised by an object variable declared using the `WithEvents` keyword.</span></span>

<span data-ttu-id="0eede-105">**ID errore:** BC30506</span><span class="sxs-lookup"><span data-stu-id="0eede-105">**Error ID:** BC30506</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="0eede-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="0eede-106">To correct this error</span></span>

<span data-ttu-id="0eede-107">Specificare la `WithEvents` variabile necessaria.</span><span class="sxs-lookup"><span data-stu-id="0eede-107">Supply the necessary `WithEvents` variable.</span></span>

## <a name="example"></a><span data-ttu-id="0eede-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="0eede-108">Example</span></span>

<span data-ttu-id="0eede-109">Nell'esempio seguente Visual Basic genera un errore del compilatore `BC30506` perché la parola chiave [WithEvents](../modifiers/withevents.md) non viene utilizzata nella definizione dell' <xref:System.Timers.Timer?displayProperty=nameWithType> istanza.</span><span class="sxs-lookup"><span data-stu-id="0eede-109">In the following example, Visual Basic generates compiler error `BC30506` because the [WithEvents](../modifiers/withevents.md) keyword is not used in the definition of the <xref:System.Timers.Timer?displayProperty=nameWithType> instance.</span></span>

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

<span data-ttu-id="0eede-110">L'esempio seguente viene compilato correttamente perché la `_timer1` variabile è definita con la `WithEvents` parola chiave:</span><span class="sxs-lookup"><span data-stu-id="0eede-110">The following example compiles successfully because the `_timer1` variable is defined with the `WithEvents` keyword:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="0eede-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0eede-111">See also</span></span>

- [<span data-ttu-id="0eede-112">Selettori</span><span class="sxs-lookup"><span data-stu-id="0eede-112">Handles</span></span>](../statements/handles-clause.md)
