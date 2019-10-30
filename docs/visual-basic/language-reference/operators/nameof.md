---
title: Operatore NameOf-Visual Basic
description: Informazioni su come usare l'operatore NameOf in Visual Basic
ms.date: 10/27/2019
helpviewer_keywords:
- NameOf operator [Visual Basic]
ms.openlocfilehash: 8416bb1a1715c1c37b62cac6a9e0b427a9c72547
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/29/2019
ms.locfileid: "73041317"
---
# <a name="nameof-operator---visual-basic"></a>Operatore NameOf-Visual Basic

L'operatore `NameOf` ottiene il nome di una variabile, di un tipo o di un membro come costante stringa:

```vb
Console.WriteLine(NameOf(System.Collections.Generic))  ' output: Generic
Console.WriteLine(NameOf(List(Of Integer)))  ' output: List
Console.WriteLine(NameOf(List(Of Integer).Count))  ' output: Count
Console.WriteLine(NameOf(List(Of Integer).Add))  ' output: Add

Dim numbers As New List(Of Integer) From { 1, 2, 3 }
Console.WriteLine(NameOf(numbers))  ' output: numbers
Console.WriteLine(NameOf(numbers.Count))  ' output: Count
Console.WriteLine(NameOf(numbers.Add))  ' output: Add
```

Come illustrato nell'esempio precedente, nel caso di un tipo e di uno spazio dei nomi, il nome prodotto in genere non è [completo](~/_csharplang/spec/basic-concepts.md#fully-qualified-names).

L'operatore `NameOf` viene valutato in fase di compilazione e non ha alcun effetto in fase di esecuzione.

È possibile usare l'operatore `NameOf` per rendere più gestibile il codice per il controllo degli argomenti:

```vb
Private _name As String

Public Property Name As String
    Get
        Return _name
    End Get
    Set
        If value Is Nothing Then
            Throw New ArgumentNullException(NameOf(value), $"{NameOf(name)} cannot be null.")
        End If
    End Set
End Property
```

L'operatore `NameOf` è disponibile in Visual Basic 14 e versioni successive.

## <a name="see-also"></a>Vedere anche

- [Riferimenti per il linguaggio Visual Basic](../index.md)
- [Operatori (Visual Basic)](index.md)
