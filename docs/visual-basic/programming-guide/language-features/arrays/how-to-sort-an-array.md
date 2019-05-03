---
title: 'Procedura: Ordinare una matrice in Visual Basic'
ms.date: 07/20/2015
f1_keywords:
- Array.Sort
helpviewer_keywords:
- arrays [Visual Basic], sorting
- examples [Visual Basic], arrays
ms.assetid: 9289aeaa-9626-4698-94a7-1d1fd3702b87
ms.openlocfilehash: 3f4dbd6dce0957de3451b1f29c3a67ccd6791045
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62053660"
---
# <a name="how-to-sort-an-array-in-visual-basic"></a>Procedura: Ordinare una matrice in Visual Basic
In questo esempio dichiara una matrice di `String` gli oggetti denominati `zooAnimals`, viene compilato e quindi la Ordina alfabeticamente.  
  
## <a name="example"></a>Esempio  
  
```  
Private Sub sortAnimals()  
    Dim zooAnimals(2) As String  
    zooAnimals(0) = "lion"  
    zooAnimals(1) = "turtle"  
    zooAnimals(2) = "ostrich"  
    Array.Sort(zooAnimals)  
End Sub  
```  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
- Accesso a mscorlib. dll e <xref:System> dello spazio dei nomi.  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Le seguenti condizioni possono generare un'eccezione:  
  
- La matrice è vuota (<xref:System.ArgumentNullException> classe)  
  
- La matrice è multidimensionale (<xref:System.RankException> classe)  
  
- Uno o più elementi della matrice non implementano le <xref:System.IComparable> interface (<xref:System.InvalidOperationException> classe)  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Array.Sort%2A?displayProperty=nameWithType>
- [Matrici](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [Risoluzione dei problemi relativi alle matrici](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)
- [Raccolte](../../concepts/collections.md)
- [Istruzione For Each...Next](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)
