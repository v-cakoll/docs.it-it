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
# <a name="handles-clause-requires-a-withevents-variable-defined-in-the-containing-type-or-one-of-its-base-types"></a>La clausola Handles richiede una variabile WithEvents definita nel tipo che la contiene o in uno dei relativi tipi di base

Non è stata fornita una `WithEvents` variabile nella `Handles` clausola. La `Handles` parola chiave alla fine di una dichiarazione di routine fa in modo che gestisca gli eventi generati da una variabile oggetto dichiarata con la `WithEvents` parola chiave.

**ID errore:** BC30506

## <a name="to-correct-this-error"></a>Per correggere l'errore

Specificare la `WithEvents` variabile necessaria.

## <a name="example"></a>Esempio

Nell'esempio seguente Visual Basic genera un errore del compilatore `BC30506` perché la parola chiave [WithEvents](../modifiers/withevents.md) non viene utilizzata nella definizione dell' <xref:System.Timers.Timer?displayProperty=nameWithType> istanza.

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

L'esempio seguente viene compilato correttamente perché la `_timer1` variabile è definita con la `WithEvents` parola chiave:

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

## <a name="see-also"></a>Vedere anche

- [Selettori](../statements/handles-clause.md)
