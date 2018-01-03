---
title: 'Procedura: ordinare una matrice in Visual Basic'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: Array.Sort
helpviewer_keywords:
- arrays [Visual Basic], sorting
- examples [Visual Basic], arrays
ms.assetid: 9289aeaa-9626-4698-94a7-1d1fd3702b87
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f24c0625058dbd960411d5981b4e98e0e9422b99
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-sort-an-array-in-visual-basic"></a>Procedura: ordinare una matrice in Visual Basic
In questo esempio dichiara una matrice di `String` gli oggetti denominati `zooAnimals`, viene compilata e quindi la Ordina alfabeticamente.  
  
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
  
-   Accesso a mscorlib. dll e <xref:System> dello spazio dei nomi.  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Le seguenti condizioni possono generare un'eccezione:  
  
-   Matrice è vuota (<xref:System.ArgumentNullException> classe)  
  
-   La matrice è multidimensionale (<xref:System.RankException> classe)  
  
-   Uno o più elementi della matrice non implementano il <xref:System.IComparable> interfaccia (<xref:System.InvalidOperationException> classe)  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Array.Sort%2A?displayProperty=nameWithType>  
 [Array](../../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [Risoluzione dei problemi relativi alle matrici](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)  
 [Raccolte](../../concepts/collections.md)  
 [Istruzione For Each...Next](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)
