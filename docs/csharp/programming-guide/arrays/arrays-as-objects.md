---
title: Matrici come oggetti (Guida per programmatori C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- arrays [C#], as objects
ms.assetid: f76d4403-bd0a-42a0-9bc8-694c55b2c926
caps.latest.revision: 17
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: e29685af509009f42f38ba2dbf8524075e880ff9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="arrays-as-objects-c-programming-guide"></a>Matrici come oggetti (Guida per programmatori C#)
In C# le matrici sono in effetti oggetti e non semplicemente aree indirizzabili di memoria contigua come in C e C++. <xref:System.Array> è il tipo di base astratto di tutti i tipi di matrice. È possibile usare le proprietà e gli altri membri di classe disponibili per <xref:System.Array>. Un esempio è l'uso della proprietà <xref:System.Array.Length%2A> per ottenere la lunghezza della matrice. Il codice seguente assegna la lunghezza della matrice `numbers`, ovvero `5`, a una variabile denominata `lengthOfNumbers`:  
  
 [!code-csharp[csProgGuideArrays#3](../../../csharp/programming-guide/arrays/codesnippet/CSharp/arrays-as-objects_1.cs)]  
  
 La classe <xref:System.Array> offre numerosi altri utili metodi e proprietà per l'ordinamento, la ricerca e la copia di matrici.  
  
## <a name="example"></a>Esempio  
 Questo esempio usa la proprietà <xref:System.Array.Rank%2A> per visualizzare il numero di dimensioni di una matrice.  
  
 [!code-csharp[csProgGuideArrays#2](../../../csharp/programming-guide/arrays/codesnippet/CSharp/arrays-as-objects_2.cs)]  
  
## <a name="see-also"></a>Vedere anche  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Array](../../../csharp/programming-guide/arrays/index.md)  
 [Matrici unidimensionali](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)  
 [Matrici multidimensionali](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)  
 [Matrici irregolari](../../../csharp/programming-guide/arrays/jagged-arrays.md)
