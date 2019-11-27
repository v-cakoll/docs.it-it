---
title: 'Procedura: ordinare una matrice'
ms.date: 07/20/2015
f1_keywords:
- Array.Sort
helpviewer_keywords:
- arrays [Visual Basic], sorting
- examples [Visual Basic], arrays
ms.assetid: 9289aeaa-9626-4698-94a7-1d1fd3702b87
ms.openlocfilehash: 3fb9af8de0fc86075fdccd64506c855c1c720660
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351846"
---
# <a name="how-to-sort-an-array-in-visual-basic"></a>Procedura: ordinare una matrice in Visual Basic

Questo articolo illustra un esempio di come ordinare una matrice di stringhe in Visual Basic.

## <a name="example"></a>Esempio

In questo esempio viene dichiarata una matrice di oggetti `String` denominati `zooAnimals`, viene popolata e quindi ordinata in ordine alfabetico:
  
```vb
Private Sub SortAnimals()
    Dim zooAnimals(2) As String
    zooAnimals(0) = "lion"
    zooAnimals(1) = "turtle"
    zooAnimals(2) = "ostrich"
    Array.Sort(zooAnimals)
End Sub
```

## <a name="robust-programming"></a>Programmazione efficiente

Le seguenti condizioni possono generare un'eccezione:

- La matrice è vuota (<xref:System.ArgumentNullException> classe).
- Array è multidimensionale (<xref:System.RankException> Class).
- Uno o più elementi della matrice non implementano l'interfaccia <xref:System.IComparable> (classe<xref:System.InvalidOperationException>).

## <a name="see-also"></a>Vedere anche

- <xref:System.Array.Sort%2A?displayProperty=nameWithType>
- [Matrici](index.md)
- [Risoluzione dei problemi relativi alle matrici](troubleshooting-arrays.md)
- [Raccolte](../../concepts/collections.md)
- [Istruzione For Each...Next](../../../language-reference/statements/for-each-next-statement.md)
