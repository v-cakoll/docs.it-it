---
title: Esempio di esecuzione posticipata
ms.date: 07/20/2015
ms.assetid: 9a22bea1-c755-4aac-800a-fcd9e5107ace
ms.openlocfilehash: 863b018b6047d61f6fb4a5c1ac68151ed69d24a1
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410799"
---
# <a name="deferred-execution-example-visual-basic"></a>Esempio di esecuzione posticipata (Visual Basic)

In questo argomento vengono illustrati gli effetti dell'esecuzione posticipata e della valutazione lazy sulle query LINQ to XML.

## <a name="example"></a>Esempio

Nell'esempio seguente è illustrato l'ordine di esecuzione quando si usa un metodo di estensione basato su esecuzione posticipata. Viene dichiarata una matrice di tre stringhe. Viene quindi scorsa la raccolta restituita da `ConvertCollectionToUpperCase`.

```vb
Imports System.Runtime.CompilerServices

Module Module1

    <Extension()>
    Private Iterator Function ConvertCollectionToUpperCase(
    ByVal source As IEnumerable(Of String)) _
    As IEnumerable(Of String)
        For Each str As String In source
            Console.WriteLine("ToUpper: source {0}", str)
            Yield str.ToUpper()
        Next
    End Function

    Sub Main()
        Dim stringArray = New String() {"abc", "def", "ghi"}

        Dim q = From str In stringArray.ConvertCollectionToUpperCase()
                Select str

        For Each Str As String In q
            Console.WriteLine("Main: str {0}", Str)
        Next
    End Sub

End Module
```

Nell'esempio viene prodotto l'output seguente:

```console
ToUpper: source abc
Main: str ABC
ToUpper: source def
Main: str DEF
ToUpper: source ghi
Main: str GHI
```

Si noti che quando si scorre la raccolta restituita da `ConvertCollectionToUpperCase`, ogni elemento viene recuperato dalla matrice di stringhe di origine e viene convertito in lettere maiuscole prima del recupero dell'elemento successivo.

L'intera matrice di stringhe non viene convertita in lettere maiuscole prima dell'elaborazione nel ciclo `foreach` di `Main` di ogni elemento della raccolta restituita.

## <a name="see-also"></a>Vedere anche

- [Esercitazione: esecuzione posticipata (Visual Basic)](tutorial-deferred-execution.md)
