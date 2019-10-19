---
title: La clausola Handles richiede una variabile WithEvents definita nel tipo che la contiene o in uno dei relativi tipi di base
ms.date: 07/20/2015
f1_keywords:
- vbc30506
- bc30506
helpviewer_keywords:
- BC30506
ms.assetid: 5b66f6a8-f050-4e03-a57f-a64e85f80cb5
ms.openlocfilehash: 191415408f607d0ff768e50c41fa9b3c4405a688
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582819"
---
# <a name="handles-clause-requires-a-withevents-variable-defined-in-the-containing-type-or-one-of-its-base-types"></a>La clausola Handles richiede una variabile WithEvents definita nel tipo che la contiene o in uno dei relativi tipi di base

Nella clausola `Handles` non è stato fornito un `WithEvents` variabile. La parola chiave `Handles` alla fine di una dichiarazione di routine fa in modo che gestisca gli eventi generati da una variabile oggetto dichiarata con la parola chiave `WithEvents`.

**ID errore:** BC30506

## <a name="to-correct-this-error"></a>Per correggere l'errore

Specificare la variabile di `WithEvents` necessaria.

## <a name="example"></a>Esempio

Nell'esempio seguente Visual Basic genera un errore del compilatore `BC30506` perché la parola chiave [WithEvents](../modifiers/withevents.md) non viene utilizzata nella definizione dell'istanza di <xref:System.Timers.Timer?displayProperty=nameWithType>.

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

L'esempio seguente viene compilato correttamente perché la variabile `_timer1` è definita con la parola chiave `WithEvents`:

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

- [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)
