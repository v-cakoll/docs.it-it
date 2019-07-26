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
# <a name="handles-clause-requires-a-withevents-variable-defined-in-the-containing-type-or-one-of-its-base-types"></a>La clausola Handles richiede una variabile WithEvents definita nel tipo che la contiene o in uno dei relativi tipi di base
Non è stata fornita una `WithEvents` variabile `Handles` nella clausola. La `Handles` parola chiave alla fine di una dichiarazione di routine fa in modo che gestisca gli eventi generati da una variabile `WithEvents` oggetto dichiarata con la parola chiave.
  
 **ID errore:** BC30506

## <a name="to-correct-this-error"></a>Per correggere l'errore
  
- Specificare la variabile `WithEvents` necessaria.
  
## <a name="example"></a>Esempio

Nell'esempio seguente Visual Basic genera un errore `BC30506` del compilatore perché la parola chiave [WithEvents](../modifiers/withevents.md) non viene utilizzata nella definizione dell' <xref:System.Timers.Timer?displayProperty=nameWithType> istanza.

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

- [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)
