---
title: Matrici come oggetti - Guida per programmatori C#
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], as objects
ms.assetid: f76d4403-bd0a-42a0-9bc8-694c55b2c926
ms.openlocfilehash: fd4496e0f84953204ad8c3f40db699e911c3f477
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/19/2019
ms.locfileid: "69597357"
---
# <a name="arrays-as-objects-c-programming-guide"></a>Matrici come oggetti (Guida per programmatori C#)

In C# le matrici sono in effetti oggetti e non semplicemente aree indirizzabili di memoria contigua come in C e C++. <xref:System.Array> è il tipo di base astratto di tutti i tipi di matrice. È possibile usare le proprietà e gli altri membri di classe disponibili per <xref:System.Array>. Un esempio è l'uso della proprietà <xref:System.Array.Length%2A> per ottenere la lunghezza della matrice. Il codice seguente assegna la lunghezza della matrice `numbers`, ovvero `5`, a una variabile denominata `lengthOfNumbers`:  
  
 [!code-csharp[csProgGuideArrays#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#3)]  
  
 La classe <xref:System.Array> offre numerosi altri utili metodi e proprietà per l'ordinamento, la ricerca e la copia di matrici.  
  
## <a name="example"></a>Esempio

 Questo esempio usa la proprietà <xref:System.Array.Rank%2A> per visualizzare il numero di dimensioni di una matrice.  
  
 [!code-csharp[csProgGuideArrays#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#2)]  
  
## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Matrici](./index.md)
- [Matrici unidimensionali](./single-dimensional-arrays.md)
- [Matrici multidimensionali](./multidimensional-arrays.md)
- [Matrici irregolari](./jagged-arrays.md)
